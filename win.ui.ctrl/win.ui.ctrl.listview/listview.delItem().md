

##示例

* **删除listview勾选的项**
	

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=343;parent=...;right=303;text="AAuto Form" )
		 winform.add( 
		 listview={ bgcolor=16777215;bottom=272;right=240;left=24;top=8;z=1;edge=1;cls="listview" };
		 button={ bottom=320;text="button";left=80;top=296;z=2;right=184;cls="button" }
		 )
		/*}}*/
		
		 winform.listview.insertColumn("时间",160,1);
		 winform.listview.fullRow=true;
		 winform.listview.setExtended(0x4/*_LVS_EX_CHECKBOXES*/);//设置复选框
		
		for(i=1;10;1){
		     winform.listview.addItem();
		     winform.listview.setItemText(tostring(i),i,1);  
		 }		
		 winform.button.oncommand = function(id,event){
			//删除要倒着从后面删除
		    for(i=winform.listview.count;1;-1){
		         if(winform.listview.getChecked(i)){  
		             winform.listview.delItem(i)
		         }   
		     }  
		 }
		 winform.listview.onnotify = function(id,code,ptr){ 
		     select(code) {
		         case  0xFFFFFFFE/*_NM_CLICK*/ {
		             if(winform.listview.selIndex){
		                 winform.listview.setChecked(winform.listview.selIndex);//勾选
		                    winform.listview.selIndex = null; 
		             }
		         }
		     }
		 }		
		 winform.show() 
		 win.loopMessage();
		 return winform;