















##示例

* **设置列宽度自适应**

		import win.ui;
		/*DSG{{*/
		var winform = win.form( right=599;bottom=399;parent=...;text="AAuto Form";border="resizable" )
		 winform.add( 
		 listview={ dr=1;dl=1;bgcolor=16777215;bottom=384;right=584;left=24;dt=1;top=16;z=1;db=1;edge=1;cls="listview" }
		 )
		/*}}*/		
		 winform.listview.insertColumn("测试列", 10);		
		 winform.adjust = function (cx, cy) {
		     winform.listview.setColumn({ cx = winform.listview.clientRect.right }, 1);
		 }		
		 winform.show() 
		 win.loopMessage();
* **listview两列宽度自适应**

		import win.ui;
		/*DSG{{*/
		var winform = win.form( right=599;bottom=399;parent=...;text="AAuto Form";border="resizable" )
		 winform.add( 
		 listview={ dr=1;dl=1;bgcolor=16777215;bottom=384;right=584;left=24;dt=1;top=16;z=1;db=1;edge=1;cls="listview" }
		 )
		/*}}*/		
		 winform.listview.insertColumn("列1", 10);		
		 winform.listview.insertColumn("列2", 10);
		 winform.adjust = function (cx, cy) {
		     winform.listview.setColumn({ cx = winform.listview.clientRect.right/2 }, 1);
		     winform.listview.setColumn({ cx = winform.listview.clientRect.right/2 }, 2);
		 }		
		 winform.show() 
		 win.loopMessage();