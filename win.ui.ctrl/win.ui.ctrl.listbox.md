#listbox-列表框控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>items</td><td>table，选项集合，以分号分隔</td></tr>
	<tr><td>msel</td><td>1/0，允许多选。用_LBS_MULTIPLESEL样式改变</td></tr>
</table>
###成员
<table>
<tr><td>add("内容")</td><td>添加列表项到尾部</td></tr>
<tr><td>add("内容",-1)</td><td>添加列表项到尾部</td></tr>
<tr><td>add("内容",1)</td><td>添加列表项到头部</td></tr>
<tr><td>addfile(__/*请输入路径*/)</td><td>向列表框里增加一个文件(包括目录)</td></tr>
<tr><td>selectRange(1,__)</td><td>选中指定范围,如果不指定任何参数，取消选区</td></tr>
<tr><td>setSelected(1__/*项索引*/)</td><td>选中指定项,索引为0则选定全部,该函数仅在开启控件多选模式下有效,单选模式下请使用selIndex属性替代</td></tr>
<tr><td>setSelected(1__/*项索引*/,false)</td><td>取消选中指定项,索引为0则取消全选</td></tr>
<tr><td>getSelected(1__/*项索引*/)</td><td>是否选中 </td></tr>
<tr><td>selIndex</td><td>获取或设置列表框当前选中项,仅在单选模式下有效,多选模式下请使用 getSelected() setSelected() 函数</td></tr>
<tr><td>selText</td><td>获取当前选项的文本,或根据指定的文本查找并改变选项。*当指定文本为"1"，若有10会选择10</td></tr>
<tr><td>getItemText(__/*项索引*/)</td><td>获取指定项文本</td></tr>
<tr><td>getItemRect(__/*项索引*/)</td><td>获取指定项区块位置,返回::RECT() 结构体</td></tr>
<tr><td>getAt(x,y)</td><td>返回指定客户区坐标所在的项索引.</td></tr>
<tr><td>hitTest(.(x坐标,y坐标,是否屏幕坐标)</td><td>该函数返回指定坐标的句柄,参数三可省略,默认为false.,如果不指定任何参数，则自动获取当前消息坐标</td></tr>
<tr><td>findEx(__/*请输入文本*/)</td><td>精确查找指定的项,找不到返回0</td></tr>
<tr><td>find(__/*请输入文本*/)</td><td>在列表框里查找指定的项,找不到返回0</td></tr>
<tr><td>count</td><td>列表项数目</td></tr>
<tr><td>items</td><td>列表项集合,table对象</td></tr>
<tr><td>delete()</td><td>删除当前选中项</td></tr>
<tr><td>delete(__)</td><td>删除指定项</td></tr>
<tr><td>clear()</td><td>清除列表框所有内容</td></tr>
</table>

####注意
* **listbox的键值对**  
  listbox的每一项有text属性，无value属性  
  可以直接给listbox自定义一个table类型的values属性，通过table.push方法把text和value存储下来

###用法
* 添加数据
	
		winform.listbox.add("内容") //添加列表项到尾部
		winform.listbox.add("内容",-1) //添加列表项到尾部
		winform.listbox.add("内容",1) //添加列表项到头部
		winform.listbox.add("内容",index) //添加列表项到指定位置

* 设置选择索引

		winform.listbox.selIndex=index;
* 读取选择索引

		winform.text = winform.listbox.selIndex;
* 选择指定范围内的项

		winform.listbox.selectRange(startIndex,endIndex);

* 编辑指定项  
  **先增加再删除**
 
		winform.listbox.add("内容",index)
		winform.listbox.delete(index+1)

* 判断指定项是否选中

		winform.listbox.getSelected(index) //返回true或false

* 根据文本查找选项

		winform.listbox.find("内容") //返回索引
		winform.listbox.findEx("内容") //返回索引
* 删除数据

		winform.listbox.delete(); //删除当前选中
		winform.listbox.delete(index);//删除指定项，index为项索引
* 删除全部项（清空全部项）

		winform.listbox.clear()

* 遍历listbox

		for(i=1;winform.listbox.count;1){
	        var txt=winform.listbox.getItemText(i)
	        win.msgbox(txt,"AAuto")
	    }

####注意
* 没有找到可以动态改是否多选的的方法，解决方案是可以设置listbox允许多选，定义一个标志变量决定是否可以多选，如果不允许就设置最后一个选择项选中，其他设置为不选中。（未验证）

##示例
* **双击列表项原地编辑效果**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		listbox={ bgcolor=16777215;bottom=192;right=284;left=75;top=36;
		items={"ddddddddddd";"cccc";"双击编辑"};z=1;text="listbox";edge=1;cls="listbox" };
		edit={ bottom=190;right=273;left=82;top=163;z=2;text="编辑";hide=1;edge=1;cls="edit" }
		)
		/*}}*/		
		win.setParent( winform.edit.hwnd,winform.listbox.hwnd )
		winform.listbox.oncommand = function(id,event){
		    if( event ==  0x2/*_LBN_DBLCLK*/ ){
		        winform.edit.selIndex = winform.listbox.selIndex ;
		        var rc = winform.listbox.getItemRect( winform.edit.selIndex )
		        rc.bottom += 5;
		        win.setRect(winform.edit.hwnd,rc) 
		        winform.edit.hide = false; 
		        winform.edit.text = winform.listbox.selText; 
		    }    
		}
		winform.edit.wndproc = function(hwnd,message,wparam,lparam){
		    ..io.print( message )
		    if( message == 0x8/*_WM_KILLFOCUS*/ 
		        || (message==0x101/*_WM_KEYUP*/ && wparam == 0xD/*_VK_ENTER*/) ) {
		        if(winform.edit.selIndex){
		            winform.listbox.add(winform.edit.text,winform.edit.selIndex)
		            winform.listbox.delete(winform.edit.selIndex+1)
		            winform.edit.hide = true;
		            winform.listbox.redraw()
		        }
		    }
		} 		
		winform.show() 
		win.loopMessage();
* **循环逐行读取listbox里的内容**

		import win.ui;
		/*DSG{{*/
		var winform = win.form( bottom=135;parent=...;right=329;text="AAuto Form" )
		 winform.add( 
		 button={ bottom=75;text="读";left=223;top=42;z=1;right=308;cls="button" };
		 listbox={ 
		 items={ "1";"2";"3" };bgcolor=16777215;bottom=105;right=211;left=38;top=26;z=2;edge=1;cls="listbox" }
		 )
		/*}}*/
		
		 winform.button.oncommand = function(id,event){
		     for(i=1;winform.listbox.count;1){
		         var txt=winform.listbox.getItemText(i)
		         win.msgbox(txt,"AAuto")
		     }
		 }
		
		winform.show() 
		win.loopMessage();
		return winform;

* **listbox显示水平滚动条**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
		listbox={ bottom=330;bgcolor=16777215;vscroll=1;right=235;left=105;top=65;z=1;
		items={  };hscroll=1;edge=1;cls="listbox" }
		)
		/*}}*/

		for(i=1;20;1){
			winform.listbox.add(string.repeat(20,tostring(i)+"-"))

		}
		::SendMessageInt( winform.listbox.hwnd,0x194/*_LB_SETHORIZONTALEXTENT*/,500,0)

		winform.show() 
		win.loopMessage();