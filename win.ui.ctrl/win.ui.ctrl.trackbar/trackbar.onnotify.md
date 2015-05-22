
#trackbar.onnotify

<table>
<tbody><tr><th>Topic</th><th>Contents</th></tr>
<tr><td>
<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb760155(v=vs.85).aspx">NM_CUSTOMDRAW (trackbar)</a>
</td><td>
<p>Sent by a trackbar control to notify its parent windows about drawing operations. This notification code is sent in the form of a <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb775583(v=vs.85).aspx"><strong xmlns="http://www.w3.org/1999/xhtml">WM_NOTIFY</strong></a> message. </p>
</td></tr>
<tr><td>
<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb760170(v=vs.85).aspx">NM_RELEASEDCAPTURE (trackbar)</a>
</td><td>
<p>Notifies a trackbar control's parent window that the control is releasing mouse capture. This notification code is sent in the form of a <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb775583(v=vs.85).aspx"><strong xmlns="http://www.w3.org/1999/xhtml">WM_NOTIFY</strong></a> message. </p>
</td></tr>
<tr><td>
<a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb760172(v=vs.85).aspx">TRBN_THUMBPOSCHANGING</a>
</td><td>
<p>Notifies that the thumb position on a trackbar is changing. This notification code is sent in the form of a <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/bb775583(v=vs.85).aspx"><strong xmlns="http://www.w3.org/1999/xhtml">WM_NOTIFY</strong></a> message.</p>
</td></tr>
</tbody></table>


##示例

* **拖动trackbar改变字体大小**  

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; right=349;text="AAuto Form";bottom=249 )
		winform.add( 
		trackbar={ bottom=217;max=100;right=291;left=44;min=0;font=LOGFONT( name="SimSun";h=-12 );z=1;text="trackbar";top=187;cls="trackbar" };
		edit={ bottom=119;color=0;text="edit";left=27;multiline=1;top=47;font=LOGFONT( name="";h=-48 );z=2;right=318;edge=1;cls="edit" }
		)
		/*}}*/

		winform.trackbar.max=48
		winform.trackbar.min=5;
		winform.trackbar.pos=15;

		winform.trackbar.onnotify = function(id,code,ptr){  
		    if(code=0xFFFFFFF4){    
		        winform.edit.setFont(h=0-winform.trackbar.pos;name="宋体");
		        winform.edit.redraw();
		    }  
		    winform.text=tostring(code,16)//当trackbar控件拖动到最大或最小时code=0xFFFFFF0
		}

		winform.show() 
		win.loopMessage();