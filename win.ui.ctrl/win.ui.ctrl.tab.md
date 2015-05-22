#tab-选项卡控件


###设计属性  
<table>	
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
</table>


###成员
<table>
	<tr><td>tab.loadForm("__/*请输入aau文件路径*/")</td><td>加载外部窗体文件并添加到tab页.,请注意保存外部窗体文件以后测试运行.</td></tr>
	<tr><td>tab.remove(__)</td><td>参数为数值，移除指定索引的选项页</td></tr>
	<tr><td>tab.removeAll()</td><td>移除所有选项卡</td></tr>
	<tr><td>tab.items</td><td>返回子窗口列表，只读属性</td></tr>
	<tr><td>tab.items[]</td><td>!winform.</td></tr>
	<tr><td>tab.adjustRect()</td><td>调整子窗口大小以适应客户区</td></tr>
	<tr><td>tab.selIndex</td><td>读取或设置当前选项索引,起始索引为1</td></tr>
	<tr><td>tab.add(__)</td><td>请先用窗体设计器生成创建窗体代码，,然后将创建窗体的win.form函数替换为此函数。,函数参数即是win.form的参数(text参数表示选项卡标题)。</td></tr>
	<tr><td>tab.hitTest(.(x坐标,y坐标,是否屏幕坐标)</td><td>返回坐标指向的选项索引,参数三可省略,默认为false.,如果不指定任何参数，则自动调用 win.getMessagePos() 获取消息坐标</td></tr>
	<tr><td>tab.setItem(__/*索引*/,"")</td><td>设置选项结构体</td></tr>
	<tr><td>tab.getItem(__/*索引*/)</td><td>读取选项结构体</td></tr>
	<tr><td>tab.setItemText(__/*索引*/,"")</td><td>设置选项卡标题</td></tr>
	<tr><td>tab.getItemText(__/*索引*/)</td><td>读取选项卡标题 </td></tr>
	<tr><td>tab.getItemRect(__/*索引*/)</td><td>读取选项卡区块位置</td></tr>
	<tr><td>win.ui.ctrl.tab.TCITEM()</td><td>选项结构体</td></tr>
</table>
###用法
* 创建tab
* 修改tab
* tab里的控件


##示例

* **Tab控件示例**

		import win;
		import win.ui; 
		import win.ui.menu
		import win.ole.image
		/*DSG{{*/
		var winform = win.form(parent=...; top=0;bottom=249;text="AAuto Form";left=0;right=349 )
		winform.add( 
		tab={ bottom=221;right=318;left=22;top=26;z=1;text="tab";edge=1;cls="tab" }
		)
		/*}}*/		
		winform.tab.onnotify = function(id,code,ptr){
		    //var nmdr = win.ui.NMHDR(); raw.convert( ptr,nmdr );
		    if(code==0xFFFFFDD9/*_TCN_SELCHANGE*/) 
		        win.msgbox("切换") 
		}//endproc		
		
		/*
		为TAB选项控件添加一个页面。
		一个页面实际上就是一个普通的窗体，可以使用窗体设计器生成，然后将win.form函数替换为winform.tab.add即可。
		仅需指定text参数(选项卡标题)，以及bottom(高度)，right(宽度)
		*/
		page = winform.tab.add(  text="选项";bottom=140;right=325 )
		page.add( 
			button={ bottom=49;text="你好";left=36;right=135;top=21;z=1;cls="button" } 
		) 
		page.button.oncommand = function(id,event){
		    win.msgbox( page.button.text,"也可以使用回调函数" ); 
		}//endproc		
		page2 = winform.tab.add(  text="点这里";bottom=140;right=325  )
		page2.add( 
		button={ bottom=49;text="Hello";left=36;right=135;top=21;z=1;cls="button" }
		) 
		page2.button.oncommand = function(id,event){
		    win.msgbox( page2.button.text,"Hello!" ); 
		}//endproc		
		winform.show(true) 
		win.loopMessage( winform );

* **设置Tab选项卡页中的控件属性**

		page = winform.tab.add(  text="选项";bottom=140;right=325 )
		page.add( 
		button={ 
			bottom=49;text="你好";left=36;right=135;top=21;z=1;cls="button" };
		 	edit={ ah=1;bottom=61;right=205;left=113;top=38;z=23;aw=1;edge=1;cls="edit" };
		 ) 
		 //这种形式的使用page.edit.text="this"就可以对选项中的控件属性进行设置

* **Tab选项卡页中的按钮**

		import win.ui;
		 var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		       tab1={ bottom=368;right=560;left=16;top=24;z=1;edge=1;cls="tab" }
		 )
		 page1 = winform.tab1.add(  text="ITEM1";bottom=128;right=224)
		 page1.add(
		       button1={ bottom=100;right=224;left=56;top=72;z=2;text="按钮";cls="button" };
		       edit={ bottom=128;text="请点击按钮";left=80;multiline=1;top=88;z=2;right=408;edge=1;cls="edit" };
		 )
		 page1.button1.oncommand = function(id,event){
		    page1.edit.text="点击成功！";
		 }
		 winform.show() 
		 win.loopMessage();

* **切换不同选项卡**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=293;parent=...;right=461;text="AAuto Form" )
		winform.add( 
		tab={ bottom=234;right=393;left=30;top=25;z=1;edge=1;cls="tab" }
		)
		/*}}*/

		winform.tab.onnotify = function(id,code,ptr){
			if(code==0xFFFFFDD9/*_TCN_SELCHANGE*/)//切换选项卡
			select(winform.tab.selIndex) {
				case 1 {
				    win.msgbox("选项卡1")
				}
				case 2 {
				    win.msgbox("选项卡2")
				}
				case 3 {
				    win.msgbox("选项卡3")
				}
			}
		}
		//添加选项卡
		page1 = winform.tab.add(text="选项卡1");
		page2 = winform.tab.add(text="选项卡2");
		page3 = winform.tab.add(text="选项卡3");

		winform.show() 
		win.loopMessage();

* **鼠标悬停到选项卡标签上提示信息**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		tab={ bottom=368;right=552;left=40;top=24;z=1;edge=1;cls="tab" }
		)
		/*}}*/

		winform.tab.add({ text = "第一页" });
		winform.tab.add({ text = "第二页" });
		winform.tab.add({ text = "第三页" });
		winform.tab.wndproc = {
			[0x200/*_WM_MOUSEMOVE*/] = function (hwnd, message, wParam, lParam) {
				winform.text = string.format(
					"鼠标悬停在第 %d 个选项卡上",
					winform.tab.hitTest( win.getMessagePos(lParam) )
				);
			}
		}
		winform.show();
		win.loopMessage();

