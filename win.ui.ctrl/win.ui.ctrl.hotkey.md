#hotkey-热键控件
   获取用户在控件上按下的按键

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
</table>
###成员
<table>
<tr><td>gethotkey()</td><td>返回两个值: 控制键码,按键码</td></tr>
<tr><td>sethotkey(__,)</td><td>参数(控制键码,按键码)</td></tr>
<tr><td>reghotkey</td><td>@.reghotkey(,	function(id,mod,vk){ ,		__/*输入响应热键的执行代码*/,	},)</td></tr>
</table>

##示例
* **基本用法**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=342;bottom=171 )
		winform.add( 
		hotkey={ bottom=37;text="hotkey";left=96;top=17;z=1;right=281;edge=1;cls="hotkey" };
		button={ bottom=116;text="注册热键";left=141;top=68;z=2;right=256;cls="button" }
		)
		/*}}*/

		winform.button.oncommand = function(id,event){

		    hkid = winform.reghotkey(function(id,mod,vk){
		        winform.msgbox("按热键了") 
		    }
		    ,winform.hotkey.gethotkey() );

		} 

		winform.show() 
		win.loopMessage();