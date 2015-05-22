

<table>
<captain>event参数</captain>
	<tr><td>_LBN_SELCHANGE</td><td> 选中项被改变</td></tr>
</table>


##示例
* **选择listbox中的项,显示到edit里**


		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		button={ bottom=225;right=281;left=147;top=190;z=3;text="button";cls="button" };
		listbox={ 
		items={  };bgcolor=16777215;bottom=113;right=322;left=35;text="listbox";top=20;z=1;edge=1;cls="listbox" };
		edit={ bottom=167;right=321;left=36;multiline=1;top=133;z=2;text="edit";edge=1;cls="edit" }
		)
		/*}}*/

		//列表框触发事件
		winform.listbox.oncommand = function(id,event){

		    //如果选项被改变
		    if( event == 0x1/*_LBN_SELCHANGE*/ ){ 
		    
		        //取当前文本
		        var str = winform.listbox.selText
		        for m in string.gmatch(str ,"(\d+)") { 
		            winform.edit.text = m
		        }
		        
		    }
		    
		}

		//添加到列表框
		winform.listbox.items = {"1";"2";"3";"4"} 

		//显示窗口
		winform.show() 
		win.loopMessage();