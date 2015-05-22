
###控件公共设计属性
<table>
	<tr><th colspan="2">标准</th></tr>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>cls：string</td><td>控件类名</td></tr>
	<tr><td>items：table</td><td>table，选项集合，以分号分隔<br/>支持：listbox、combobox、checklist</td></tr>
	<tr><td>text：string</td><td>string，文本，指定窗口显示的文本<br/>支持：static、button、edit、richedit、checkbox、radiobutton、groupbox、combobox</td></tr>
	<tr><th colspan="2">外观</th></tr>
	<tr><td>hide：boolean</td><td>是否显示控件。可用hide属性或show()方法改变</td></tr>
	<tr><td>border：boolean</td><td>控件是否有细的边框。可用_WS_BORDER样式改变</td></tr>
	<tr><td>edge：boolean</td><td>控件是否有一个带阴影的边界，可用_WS_EX_STATICEDGE改变</td></tr>
	<tr><td>frame：boolean</td><td>控件是否有双层边框。可用_WS_EX_DLGMODALFRAME样式改变</td></tr>	
	<tr><td>font:：struct</td><td>LOGFONT( strike=1;underline=1;h=-9;name='Verdana';weight=700;italic=255 )。可用setFont()改变</td></tr>
	<tr><td>color：number</td><td>设置文字颜色。可用setFont(color=数值)改变</td></tr>
	<tr><td>bgcolor：number</td><td>number，设置背景颜色，可用bgcolor改变(部分控件不显示背景色)</td></tr>
	<tr><td>transparent：boolean</td><td>是否使用透明背景</td></tr>	
	<tr><td>left：number</td><td>number，指定控件的左部坐标</td></tr>
	<tr><td>right：number</td><td>number，指定控件的右部坐标</td></tr>
	<tr><td>top：number</td><td>number，指定控件的顶部坐标</td></tr>
	<tr><td>bottom：number</td><td>number，指定控件的底部坐标</td></tr>	
	<tr><td>hscroll：boolean</td><td>1/0是否显示横向滚动条<br/>
	支持：edit、richedit、listbox、combobox、checklist、listview、treeview</td></tr>
	<tr><td>vscroll：boolean</td><td>1/0是否显示竖向滚动条<br/>
	支持：edit、richedit、listbox、combobox、checklist、listview、treeview</td></tr>
	<tr><th colspan="2">行为</th></tr>	
	<tr><td>acceptfiles：boolean</td><td>允许拖放文件到该窗口并响应_WM_DROPFILES消息</td></tr>
	<tr><td>group：boolean</td><td>创建一个控件组、并将此控件作为控件组的第一个控件.可用_WS_GROUP改变</td></tr>
	<tr><td>cp：boolean</td><td>允许用户使用Tab键在窗口的子窗口间搜索。可用_WS_EX_CONTROLPARENT改变</td></tr>
	<tr><td>tabstop：boolean</td><td>用户按下Tab键时可以获得并移动键盘焦点。可用_WS_TABSTOP改变 </td></tr>
	<tr><td>help：boolean</td><td>窗口是否启用帮助支持并响应_WM_HELP消息</td></tr>
	<tr><td>disabled：boolean</td><td>是否禁用使用该控件。可用disabled属性禁用</tr>
	<tr><td>aw：boolean</td><td>窗口改变大小时，是否自动调整控件宽度。可用aw改变</td></tr>
	<tr><td>ah：boolean</td><td>窗口改变大小时，是否自动调整控件高度。可用ah改变</td></tr>
	<tr><td>dl：boolean</td><td>窗口改变大小时，是否保持左边距不变。可用dl改变</td></tr>
	<tr><td>dr：boolean</td><td>窗口改变大小时，是否保持右边距不变。可用dr改变</td></tr>
	<tr><td>dt：boolean</td><td>窗口改变大小时，是否保持顶边距不变。可用dt改变</td></tr>
	<tr><td>db：boolean</td><td>窗口改变大小时，是否保持底边距不变。可用db改变</td></tr>
	<tr><th colspan="2">其他</th></tr>
	<tr><td>align：string</td><td>水平对齐：左边对齐(left)、右边对齐(right)，中间对齐(center)。可用样式改变<br/>
		支持：static、button、edit、richedit	</td></tr>
</table>

###控件公共成员
<table>
<tr><td>cls</td><td>设计时类名</td></tr>
<tr><td>className</td><td>运行时类名</td></tr>
<tr><td>text</td><td>可读写，文本属性<br/>支持：static、button、edit、richedit、checkbox、radiobutton、groupbox、combobox<td></td>
<tr><td>hwnd</td><td>控件句柄</td></tr>
<tr><td>id</td><td>控件ID</td></tr>
<tr><td>_parentForm</td><td>控件所在的父窗口(指win.form对象)</td></tr>
<tr><td>hide</td><td>控件是否隐藏</td></tr>
<tr><td>disabled</td><td>是否禁用</td></tr>
<tr><td>left</td><td>左侧坐标</td></tr>
<tr><td>right</td><td>右侧坐标</td></tr>
<tr><td>top</td><td>顶部坐标</td></tr>
<tr><td>bottom</td><td>底部坐标</td></tr>
<tr><td>width</td><td>宽度</td></tr>
<tr><td>height</td><td>高度</td></tr>
<tr><td>theme</td><td>外观主题,例如,winform.button.theme = "Explorer",winform.button.theme = false</td></tr>
<tr><td>capture</td><td>是否捕获全局鼠标消息</td></tr>
<tr><td>getParent()</td><td>返回父窗口</td></tr>
<tr><td>setParent(/*窗口对象*/)</td><td>改变父窗口</td></tr>
<tr><td>setFocus()</td><td>设置焦点</td></tr>
<tr><td>show()</td><td>显示控件</td></tr>
<tr><td>getRect()</td><td>获取控件区块位置(::RECT结构体)</td></tr>
<tr><td>setRect(rc)</td><td>设置控件屏幕区块位置(::RECT结构体) </td></tr>
<tr><td>getClientRect()</td><td>获取控件客户区块位置(::RECT结构体),rect.</td></tr>
<tr><td>clientRect</td><td>获取控件客户区块位置(::RECT结构体)</td></tr>
<tr><td>setPos(x坐标,y坐标,宽,高,插入位置,参数)</td><td>调整窗口位置或排序,所有参数可选,同时指定x,y坐标则移动位置,同时指定宽高则改变大小,指定插入位置(句柄或_HWND前缀常量)则调整Z序</td></tr>
<tr><td>getPos()</td><td>返回相对坐标,宽,高,x,y,cx,cy=win.getPos(hwnd)</td></tr>
<tr><td>getFont()</td><td>获得控件字体(::LOGFONT结构体)</td></tr>
<tr><td>setFont()</td><td>指定LOGFONT字体对象,或逻辑字体句柄</td></tr>
<tr><td>modifyStyle(remove,add)</td><td></td></tr>
<tr><td>modifyStyleEx(remove,add)</td><td></td></tr>
<tr><td>redraw()</td><td>刷新</td></tr>
<tr><td>close()</td><td>关闭控件</td></tr>
</table>

###winform知识点

* 分组问题
* Z序问题



##示例

* **动态创建和销毁窗口内的控件**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		button={ bottom=218;right=154;left=61;top=191;font=LOGFONT( name="宋体";h=-12 );z=1;text="创建";cls="button" };
		button2={ bottom=218;right=278;left=182;top=189;font=LOGFONT( name="宋体";h=-12 );z=2;text="销毁";cls="button" }
		)
		/*}}*/		
		winform.button2.oncommand = function(id,event){
			//win.msgbox( winform.button2.text );
			winform.edit.close();		
		}		
		winform.button.oncommand = function(id,event){
			//win.msgbox( winform.button.text );
			winform.add( 
			edit={ bottom=60;right=305;left=39;top=31;font=LOGFONT( name="宋体";h=-12 );z=1;text="本文本框动态创建、销毁";edge=1;cls="edit" }
			); 		
		}		
		winform.show() 
		win.loopMessage();
		return winform;

* **一次隐藏多个控件**

* **控件的删除和销毁**
		
		winform.控件id.close();//此时可删除控件,但仍通过变量访问
		winform.控件id=null;//此时可销毁控件, 不能再访问



* **改变父窗体后的事件响应**  

		/*第一种方法
		oncommand是父窗体转发给控件的，你修改了父窗体，这机制就会失效。
		设定父窗体以后，应当使用控件的消息回调来处理事件。
		或者在父窗体中使用 winform.cmdTranslate()函数触发命令，如下：
		*/

		import win.ui;
		/*DSG{{*/
		var winform = win.form( bottom=520;parent=...;text="AAuto Form";right=713 )
		winform.add( 
		button={ bottom=178;text="button";left=92;top=103;z=4;right=211;cls="button" };
		checkbox={ bottom=156;text="checkbox";left=372;top=126;z=2;right=500;cls="checkbox" };
		richedit={ bottom=348;text="richedit";left=236;multiline=1;top=265;z=3;right=376;edge=1;cls="richedit" };
		static_viewid={ bottom=443;text="static";left=46;top=30;z=1;notify=1;right=652;transparent=1;cls="static" }
		)
		/*}}*/

		winform.static_viewid.wndproc = function(hwnd,message,wParam,lParam){
		    winform.cmdTranslate(hwnd,message,wParam,lParam);
		} 

		winform.button.setParent(winform.static_viewid)
		winform.richedit.setParent(winform.static_viewid)
		winform.checkbox.setParent(winform.static_viewid)
		  
		winform.button.oncommand = function(id,event){
		win.msgbox( winform.button.text );
		}
		winform.show() 
		win.loopMessage();
		return winform;
		/*******************/
		//第二种

				
		import win.ui;
		/*DSG{{*/
		var winform = win.form( bottom=520;parent=...;right=713;text="AAuto Form" )
		winform.add( 
		checkbox={ bottom=156;right=500;left=372;top=126;z=2;text="checkbox";cls="checkbox" };
		button={ bottom=142;right=209;left=90;top=67;z=4;text="button";cls="button" };
		richedit={ bottom=348;text="richedit";left=236;multiline=1;top=265;z=3;right=376;edge=1;cls="richedit" };
		static_viewid={ notify=1;right=652;left=46;top=30;transparent=1;bottom=443;text="static";z=1;cls="static" }
		)
		/*}}*/
		GetDlgCtrlID = ::User32.api("GetDlgCtrlID","int(int hwnd)")

		winform.button.setParent(winform.static_viewid)
		winform.richedit.setParent(winform.static_viewid)
		winform.checkbox.setParent(winform.static_viewid)

		winform.static_viewid.wndproc = function(hwnd,message,wParam,lParam){

		if(message   ==   0x111/*_WM_COMMAND*/   &&   ::LOWORD(wParam)  ==GetDlgCtrlID(winform.button.hwnd)){
		    win.msgbox("button","AAuto")
		}


		if (message   ==   0x111/*_WM_COMMAND*/   &&   ::LOWORD(wParam)  ==GetDlgCtrlID(winform.checkbox.hwnd)){
		win.msgbox("checkbox","AAuto")
		  
		}

		} 
		winform.show() 
		win.loopMessage();
		return winform;