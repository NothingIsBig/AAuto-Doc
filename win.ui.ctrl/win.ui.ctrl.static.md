#static-静态文本控件



###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
	<tr><td>center</td><td>1/0，是否启用垂直居中，启用则自动禁止文本换行。可用_SS_样式改变</td></tr>
	<tr><td>nWrap</td><td>1/0，禁用自动换行，并强制左对齐，设为false则在文本超出宽度时在空格、制表符等位置自动换行</td></tr>
	<tr><td>notify</td><td>1/0，是否启用事件回调函数oncommand</td></tr>
</table>


###成员
<table>
<tr><td>text</td><td>string，可读写，控件文本</td></tr>
<tr><td>_embedObject</td><td>嵌入OLE控件对象,embedObject.</td></tr>
<tr><td>createEmbed(.("类名",容器对象)</td><td>嵌入OLE控件,容器对象哦可选参数,返回容器对象,</td></tr>
<tr><td>createEmbed()</td><td>embedObject.</td></tr>
<tr><td>setRedraw(false)</td><td>禁止重绘</td></tr>
<tr><td>setRedraw(true)</td><td>恢复重绘</td></tr>
<tr><td>redrawTransparent()</td><td>刷新,透明背景时请使用此函数替代redraw()</td></tr>
</table>


###样式
<TABLE>
<tr><td>SS\_BLACKFRAME<td>指定了一个带边框的方框，用与窗口边框相同的颜色画出。缺省的颜色是黑色。
<tr><td>SS\_BLACKRECT<td>指定一个矩形，用窗口边框的颜色填充。缺省颜色是黑色。
<tr><td>SS\_CENTER<td>指定一个简单的矩形，在矩形的中央显示给定的文本。文本将在显示之前格式化。超出行尾的单词将自动折回到下一行的开始。
<tr><td>SS\_GRAYFRAME<td>指定一个带边框的方框，用屏幕的背景色（桌面颜色）画出。缺省的颜色是灰色。
<tr><td>SS\_GRAYRECT<td>指定一个矩形，用屏幕的背景色填充。缺省的颜色是灰色。
<tr><td>SS\_ICON<td>指定了在对话框中显示的图标。给定的文本是资源文件中定义的图标名（不是文件名）。nWidth和nHeight参数被忽略，图标自动调整自己的大小。
<tr><td>SS\_LEFT<td>指定一个简单的矩形，在矩形内显示左对齐的给定文本。文本在显示之前格式化。超出行尾的单词将自动折回到下一行的开始。
<tr><td>SS\_LEFTNOWORDWRAP<td>指定一个简单的矩形，在矩形内显示左对齐的给定文本。制表符被扩展，但是不会折回单词。超出行尾的单词被裁剪。
<tr><td>SS\_NOPREFIX<td>除非指定了这个风格，否则Windows将控制文本中所有的“&”字符解释为加速键前缀。在这种情况下，“&”被移去，字符串中的下一个字符被加上下划线。如果一个包含文本的静态文本控件不需要这个特性，可能需要加入SS_NOPREFIX。这个风格可以用于任何静态控件。你可以用位或操作符把SS_NOPREFIX与其它风格组合起来。最常使用这个风格的情况是，可能要在对话框的静态控件中显示带有“&”字符的文件名或其它字符串。
<tr><td>SS\_RIGHT<td>指定一个简单的矩形，在矩形内显示右对齐的给定文本。文本在显示之前格式化。超出行尾的单词将自动折回到下一行的开始。
<tr><td>SS\_SIMPLE<td>指定一个简单的矩形，在矩形内显示一行左对齐的文本。文本行不能用任何方法缩短或改变。（控件的父窗口或对话框不能处理WM_CTLCOLOR消息）
<tr><td>SS\_USERITEM<td>指定一个用户自定义的项。
<tr><td>SS\_WHITEFRAME<td>指定一个带边框的方框，用窗口背景色画出。缺省值为白色。
<tr><td>SS\_WHITERECT<td>指定一个矩形，用窗口背景色填充。缺省值为白色。
</TABLE>
###用法
* 设置显示文本

		winform.static.text = "要显示的文本";
* 获取显示文本

		io.open()
		io.print(winform.static.text);
* 设置字体颜色  

		//设计方式如下
		color=数值;
		//代码方式如下
		winform.static.setFont(color=22222);
		
* 设置背景颜色  
	设置背景要设置transparent=0;

		winform.static.bgcolor=255255


## 示例集

* **设置static控件字体(字体是LOGFONT结构体)**

* **static做链接，鼠标变手形**

		import win.ui;
		 /*DSG{{*/
		 var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		 static={ dr=1;text="快手网 www.aau.cn";notify=1;color=16711680;nWrap=1;left=187;bottom=149;top=135;font=LOGFONT( underline=1 );transparent=1;db=1;right=302;z=1;cls="static" }
		 )
		 /*}}*/		
		 import win.cur;
		 //当鼠标指针移到静态控件上是，切换鼠标为手形
		 var hand = win.cur.load(32649/*_IDC_HAND*/)
		 winform.static.wndproc = function(hwnd,message,wParam,lParam){
		 	if(message = 0x200/*_WM_MOUSEMOVE*/) { 
			 win.cur.setCur(hand);
		 } 
		 }//endproc		
		 winform.static.oncommand = function(id,event){
		 	import process;
			 process.execute("http://www.aau.cn")
		 }
		 winform.show() 
		 win.loopMessage();

* **后台抓图**

		//后台抓图
		//作者:lujjjh 
		import win.ui;
		import winex;
		import win.graphics;
		/*DSG{{*/
		var winform = ..win.form( bottom=446;parent=...;text="AAuto 后台截图演示";right=570 )
		winform.add( 
		picturebox={ dr=1;dl=1;notify=1;right=560;left=16;dt=1;top=32;font=LOGFONT( name='宋体' );transparent=1;db=1;bottom=432;z=2;cls="picturebox" };
		cbxWindowList={ dr=1;dl=1;vscroll=1;bottom=28;right=507;left=16;dt=1;
		items={  };font=LOGFONT( name='宋体' );text="combobox";z=1;top=8;mode="dropdownlist";edge=1;cls="combobox" };
		but_save={ disabled=1;bottom=28;text="保存";left=517;top=8;z=3;right=559;cls="button" }
		)
		/*}}*/
		winform.but_save.oncommand = function(id,event){
			import gdip;
			var image = gdip.bitmap(winform.picturebox.image);
			image.save("/test.jpg")
		}
		// 程序初始化
		(function () {
		    // 列出所有顶级窗口
		    winform.cbxWindowList.clear();
		    winex.enumTop(
		        function (hwnd) {
		            if( ! win.isVisible(hwnd)
		                || win.isIconic(hwnd) )
		                return;
		            var title = win.getText(hwnd);
		            if (#title && title!="Program Manager") {
		                winform.cbxWindowList.add(title);
		                ::SendMessageInt(winform.cbxWindowList.hwnd, 0x151/*_CB_SETITEMDATA*/, winform.cbxWindowList.count - 1, hwnd);
		            }
		        }
		    );
		    // 初始化 canvas
		    canvas = win.graphics.canvas();
		    canvas.fromWindow(winform.picturebox);
		})();
		winform.picturebox.wndproc = function (hwnd, message, wParam, lParam) {
		    if (message == 0xF/*_WM_PAINT*/) {
		        var hwnd = ::SendMessageInt(winform.cbxWindowList.hwnd, 0x150/*_CB_GETITEMDATA*/, winform.cbxWindowList.selIndex - 1, 0);
		        canvas.beginPaint();
		        canvas.printWindow(hwnd);
		        canvas.endPaint();        
		        return 1;
		    }
		}
		winform.cbxWindowList.oncommand = function(id,event){
		    if (event == 0x9/*_CBN_SELENDOK*/){
		        winform.picturebox.redraw();
		        winform.but_save.disabled = false;
		        }
		}
		winform.show();
		win.loopMessage();
		canvas.destroy()


* **创建wmplay播放器**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( right=337;bgcolor=16576749;bottom=227;parent=...;text="AAuto Form" )
		winform.add( 
		btnPlay={ dr=1;bottom=205;right=115;left=27;top=178;z=2;db=1;text="播放";cls="button" };
		static={ dr=1;dl=1;bottom=165;right=308;left=32;dt=1;top=16;z=1;db=1;transparent=1;edge=1;cls="static" };
		btnStop={ dr=1;bottom=205;right=219;left=131;top=178;z=3;db=1;text="停止";cls="button" };
		btnDump={ dr=1;bottom=205;right=318;left=230;top=178;z=4;db=1;text="显示成员";cls="button" }
		)
		/*}}*/

		//创建控件
		var wmplay = winform.static.createEmbed("{6BF52A52-394A-11d3-B153-00C04F79FAA6}");    
		wmplay._object.Url  = "http://zhangmenshiting.baidu.com/service/a401799ff13071c881685a0d087a6c43.mp3?xcode=39a942cab41dd7d1071ffa1269adcc9121"

		winform.btnStop.oncommand = function(id,event){ 
		    wmplay._object.controls.stop() 
		}
		winform.btnPlay.oncommand = function(id,event){ 
		    wmplay._object.controls.play()
		}
		winform.btnDump.oncommand = function(id,event){
		    io.open()
		    com.DumpTypeInfo(wmplay._object) 
		    execute("pause") //按任意键继续
		    io.close();//关闭控制台
		} 

		winform.show(true) 
		win.loopMessage();
		return winform;



