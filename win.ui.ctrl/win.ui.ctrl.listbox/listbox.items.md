

##示例
* **获取listbox中的所有值**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		 winform.add( 
		 button={ bottom=237;text="button";left=131;top=204;z=1;right=291;cls="button" };
		 listbox={ bgcolor=16777215;bottom=163;text="listbox";left=34;
		 items={ "1";"2";"3" };top=50;z=3;right=151;edge=1;cls="listbox" };
		 edit={ bottom=164;text="edit";left=187;multiline=1;top=20;z=2;right=328;edge=1;cls="edit" }
		 )
		/*}}*/
		
		 winform.button.oncommand = function(id,event){ 
		         winform.edit.text = table.tostring( winform.listbox.items ) 
		 } 
		 winform.show() 
		 win.loopMessage();