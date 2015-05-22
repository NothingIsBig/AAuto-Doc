


##示例
* **列出listbox中的选中项**

		import console;
		import win.ui;
		/*DSG{{*/
		var winform = win.form( text="复选列表框 响应通知消息演示";bottom=323;parent=...;right=358;max=false )
		 winform.add( 
		 button={ bottom=297;right=289;left=46;top=254;z=3;text="列出选中项目";cls="button" };
		 checklist={ bgcolor=16777215;bottom=224;right=326;left=20;top=45;z=1;
		 items={  };edge=1;cls="checklist" };
		 static={ bottom=45;right=268;left=22;top=21;z=2;transparent=1;text="请点选项目";cls="static" }
		 )
		/*}}*/
		
		 winform.checklist.items = { "测试项目";"测试项目2";"测试项目3" }   
		 winform.checklist.addItem("测试项目4")  
		 winform.checklist.addItem("测试项目5") 		
		 winform.checklist.setChecked(2);
		 winform.checklist.setChecked(3);
		 winform.checklist.setChecked(5);		
		 winform.button.oncommand = function(id,event){
		     //winform.msgbox( winform.button.text );
		    var count=winform.checklist.count;
		     for(i=1;count;1){
		         if(winform.checklist.getChecked(i)){
		             console.log("第"++i++"项:"++winform.checklist.getItemText(i,1))
		         }
		     }   
		 }		
		 winform.show() 
		 win.loopMessage();