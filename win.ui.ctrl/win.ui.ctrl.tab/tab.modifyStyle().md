#modifyStyle(remove,add)


<table>
<tr><td>_TCS_SCROLLOPPOSITE</td><td>1</td><td></td></tr>
<tr><td>_TCS_BOTTOM</td><td>2</td><td>把标签显示在下面</td></tr>
<tr><td>_TCS_RIGHT</td><td>2</td><td></td></tr>
<tr><td>_TCS_MULTISELECT</td><td>4</td><td></td></tr>
<tr><td>_TCS_FLATBUTTONS</td><td>8</td><td></td></tr>
<tr><td>_TCS_FORCEICONLEFT</td><td>0x10</td><td></td></tr>
<tr><td>_TCS_FORCELABELLEFT</td><td>0x20</td><td></td></tr>
<tr><td>_TCS_HOTTRACK</td><td>0x40</td><td></td></tr>
<tr><td>_TCS_VERTICAL</td><td>0x80</td><td></td></tr>
<tr><td>_TCS_TABS</td><td>0</td><td></td></tr>
<tr><td>_TCS_BUTTONS</td><td>0x100</td><td></td></tr>
<tr><td>_TCS_SINGLELINE</td><td>0</td><td></td></tr>
<tr><td>_TCS_MULTILINE</td><td>0x200</td><td></td></tr>
<tr><td>_TCS_RIGHTJUSTIFY</td><td>0</td><td></td></tr>
<tr><td>_TCS_FIXEDWIDTH</td><td>0x400</td><td></td></tr>
<tr><td>_TCS_RAGGEDRIGHT</td><td>0x800</td><td></td></tr>
<tr><td>_TCS_FOCUSONBUTTONDOWN</td><td>0x1000</td><td></td></tr>
<tr><td>_TCS_OWNERDRAWFIXED</td><td>0x2000</td><td></td></tr>
<tr><td>_TCS_TOOLTIPS</td><td>0x4000</td><td></td></tr>
<tr><td>_TCS_FOCUSNEVER</td><td>0x8000</td><td></td></tr>
</table>


##示例
* **隐藏tab的表头**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		 tab={ top=12;bottom=320;z=1;right=588;left=16;cls="tab" };
		 button={ bottom=368;right=364;left=224;top=340;z=2;text="切换到第二页";cls="button" }
		 )
		/*}}*/
		
		var page1 = winform.tab.add( mode="child";bottom=207;parent=...;right=427;text="AAuto Form" );
		 page1.add( 
		     button={ bottom=144;text="页面一";left=76;top=60;z=1;right=320;cls="button" }
		 );
		var page2 = winform.tab.add( mode="child";bottom=207;parent=...;right=427;text="AAuto Form" );
		 page2.add( 
		     button={ bottom=154;text="页面二";left=86;top=70;z=1;right=330;cls="button" }
		 );		
		// 隐藏表头
		winform.tab.modifyStyle(, 0x100|0x400|0x8000/*_TCS_BUTTONS|_TCS_FIXEDWIDTH|_TCS_FOCUSNEVER*/);
		 ::SendMessageInt(winform.tab.hwnd, 0x1329/*_TCM_SETITEMSIZE*/, 0, ::MAKELONG(0, 1));		
		 winform.button.oncommand = function(id,event){
		     winform.tab.selIndex = 2;
		 }		
		 winform.show();
		 win.loopMessage();

* **tab标签移到左边**

