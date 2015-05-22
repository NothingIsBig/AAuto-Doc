#splitter-拆分控件

###设计属性
<table>

	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>horz</td><td>1/0，显示方向，0：垂直，1：水平</td></tr>
</table>

###成员
<table>
	<tr><td>ltControl</td><td>左边或上边的控件\n!static.</td></tr>
	<tr><td>rbControl</td><td>右边或下边的控件\n!static.</td></tr>
	<tr><td>split(前面的控件,后面的控件)</td><td>指定需要拆分的控件,\n被折分的控件可在控件属性中指定是否支持自动调整大小</td></tr>
	<tr><td>horz</td><td>是否水平拆分条</td></tr>
	<tr><td>ltMin</td><td>前面的控件最小尺寸</td></tr>
	<tr><td>rbMin</td><td>后面的控件最小尺寸</td></tr>
	<tr><td>translateAccelerator</td><td>@.translateAccelerator - function(msg){ \n	__/*返回是否快捷键*/\n} </td></tr>
</table>

##示例

* **splitter基本应用**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=396;parent=...;text="使用拆分控件";right=406 )
		winform.add( 
		edit1={ dr=1;dl=1;text="edit1";bottom=65;right=382;left=23;multiline=1;top=12;z=1;edge=1;cls="edit" };
		splitter1={ dr=1;dl=1;bottom=71;right=382;left=23;top=66;z=4;horz=1;cls="splitter" };
		splitter2={ dr=1;dl=1;bottom=183;right=382;left=23;top=178;z=5;horz=1;cls="splitter" };
		edit3={ dr=1;dl=1;bottom=382;text="edit3";right=382;left=23;multiline=1;top=185;z=3;db=1;edge=1;cls="edit" };
		edit2={ dr=1;dl=1;bottom=176;text="edit2";right=382;left=23;multiline=1;top=72;z=2;ah=1;edge=1;cls="edit" }
		)
		/*}}*/

		winform.splitter1.split( winform.edit1,winform.edit2 )
		winform.splitter2.split( winform.edit2,winform.edit3 ) 

		winform.splitter1.ltMin = 20;
		winform.splitter1.rbMin = 30;
		winform.splitter2.ltMin = 40;
		winform.splitter2.rbMin = 50;

		winform.show() 
		win.loopMessage();
