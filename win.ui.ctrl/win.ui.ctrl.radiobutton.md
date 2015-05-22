#radiobutton-单选控件
###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
	<tr><td>checked</td><td>1/0，是否选中状态</td></tr>
</table>

###成员
<table>
	<tr><td>checked</td><td>读写，复选框是否选中状态</td></tr>
</table>

##示例
* **radiobutton分组**		
	如果你有radiobutton1－radiobutton6个,	想按radiobutton1－radiobutton3，radiobutton4－radiobutton6分成两组,那么你把radiobutton1、radiobutton4的“编组”属性设为“TRUE”即可,z序排在4之前的是一组，4之后的radiobutton就归另一组了。
	可以点右键前后排序调整z序

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=149;parent=...;text="AAuto Form";right=448 )
		winform.add( 
			radiobutton={ checked=1;bottom=46;group=1;right=95;left=34;top=29;z=1;text="radiobutton";cls="radiobutton" };
			radiobutton2={ bottom=46;text="radiobutton";left=135;top=29;z=2;right=196;cls="radiobutton" };
			radiobutton3={ bottom=46;text="radiobutton";left=235;top=29;z=3;right=296;cls="radiobutton" };
			radiobutton4={ bottom=46;text="radiobutton";left=336;top=29;z=4;right=397;cls="radiobutton" };
			radiobutton5={ checked=1;bottom=98;group=1;right=96;left=35;top=77;z=5;text="radiobutton";cls="radiobutton" };
			radiobutton8={ bottom=94;text="radiobutton";left=336;top=77;z=8;right=397;cls="radiobutton" };
			radiobutton6={ bottom=94;text="radiobutton";left=134;top=77;z=6;right=195;cls="radiobutton" };
			radiobutton7={ bottom=94;text="radiobutton";left=234;top=77;z=7;right=295;cls="radiobutton" }
		)
		/*}}*/		
		winform.show() 
		win.loopMessage();