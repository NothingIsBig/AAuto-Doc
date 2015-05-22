#modifyStyle

###用法


* 去掉边框

		winform.picturebox.modifyStyle( 0x800000/*_WS_BORDER*/)
		winform.picturebox.setPos(,,,,,0x20/*_SWP_FRAMECHANGED*/)

* 加上边框

		winform.picturebox.modifyStyle( ,0x800000/*_WS_BORDER*/)
		winform.picturebox.setPos(,,,,,0x20/*_SWP_FRAMECHANGED*/)