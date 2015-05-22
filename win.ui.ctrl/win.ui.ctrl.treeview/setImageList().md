




##示例
* **treeview控件增加小图标**

		var imageList = win.imageList(16,15).add("\res\iml.gif",0xFF00FF/*透明色*/)
		 winform.treeview.setImageList( imageList,0/*_TVSIL_NORMAL*/ )		
		 winform.treeview.insertItem(
		     text="内核库";
		     iImage=7;//数字是图标索引
		    iSelectedImage=1;
		     children={
		         {text="math";iSelectedImage=1;};
		         {text="com";iSelectedImage=1;};
		         {text="io";iSelectedImage=1;};
		         {text="raw";iSelectedImage=1;};
		         {text="string";iSelectedImage=1;};
		         {text="table";iSelectedImage=1;};
		         {text="time";iSelectedImage=1;};
		     }
		 )