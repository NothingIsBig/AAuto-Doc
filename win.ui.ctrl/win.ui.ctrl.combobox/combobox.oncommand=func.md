

##示例
* **改变combobox选中项后,显示不同内容**

		import win.ui;
		 /*DSG{{*/
		 var winform = ..win.form( bottom=225;parent=...;right=393;text="AAuto Form" )
		 winform.add( 
		 edit={ bottom=163;right=297;left=95;multiline=1;top=116;z=2;edge=1;cls="edit" };
		 combobox={ bottom=72;text="combobox";left=98;top=52;right=305;z=1;
		 items={ "a";"b";"c" };mode="dropdownlist";edge=1;cls="combobox" }
		 )
		 /*}}*/
		 io.open()
		 winform.combobox.oncommand = function(id,event){
		     var txt = winform.combobox.selText
			 if(event == 0x1/*_CBN_SELCHANGE*/){
			     select( txt ) {
			         case "a" {
			             winform.edit.text = "A";
			             io.print("di")
			         }
			         case "b" {
			             winform.edit.text = "B";
			         }
			         case "c" {
			             winform.edit.text = "C";
			         }
			     }		         
			 }
		 }
		 winform.show() 
		 win.loopMessage();