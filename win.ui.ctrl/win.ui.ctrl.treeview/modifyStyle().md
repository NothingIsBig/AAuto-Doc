#modifyStyle����


##ʾ��

* **ѡ������**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=239;parent=...;right=311;text="AAuto Form" )
		winform.add( 
		treeview={ bgcolor=16777215;bottom=232;right=304;asel=false;fullRow=1;top=8;z=1;left=8;cls="treeview";exstyle=512 }
		)
		/*}}*/
		winform.treeview.modifyStyle(0x0002,0x1000)
		var root = winform.treeview.insertItem("���ڵ�");
		winform.treeview.insertItem("�ӽڵ�һ", root);
		winform.treeview.insertItem("�ӽڵ�һ", root);
		winform.treeview.insertItem("�ӽڵ�һ", root);
		winform.treeview.insertItem("�ӽڵ�һ", root);
		winform.treeview.insertItem("�ӽڵ�һ", root);
		winform.show();
		win.loopMessage();