#trackbar-跟踪条控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
<tr><td>min</td><td>number，最小值</td></tr>
<tr><td>max</td><td>number，最大值</td></tr>
</table>

###成员
<table>
	<tr><td>pos</td><td>滑块位置</td></tr>
	<tr><td>max</td><td>最大值</td></tr>
	<tr><td>min</td><td>最小值</td></tr>
	<tr><td>setTick(__/*刻度*/)</td><td>显示设置刻度标记位置 </td></tr>
	<tr><td>setFrequency(2)</td><td>刻度标记间隔,必须在样式中指定自动刻度标记</td></tr>
	<tr><td>setRange(min,max__)</td><td>设置最小、最大刻度</td></tr>
	<tr><td>setSel(min,max__)</td><td>设置选区</td></tr>
</table>

##示例
* **拖动trackbar改变edit的字体大小**

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
		}		
		winform.show() 
		win.loopMessage();

* **用trackbar演示红绿蓝配色效果**

		import win.ui;
		 /*DSG{{*/		
		 var winform = ..win.form( text="AAuto Form";bottom=249;parent=...;right=534 )
		 winform.add( 
		 trackbar={ bgcolor=255;bottom=79;max=255;right=278;left=38;min=0;z=1;top=49;cls="trackbar" };
		 edit={ bottom=169;text="                                                                        ";left=360;multiline=1;top=92;z=8;right=429;edge=1;cls="edit" };
		 static={ bottom=83;color=0;right=332;left=297;top=55;font=LOGFONT( h=-20 );center=1;transparent=1;text="static";z=2;cls="static" };
		 static2={ bottom=141;color=0;text="static";left=297;top=113;font=LOGFONT( h=-20 );center=1;z=5;right=332;transparent=1;cls="static" };
		 static4={ bottom=82;right=426;left=360;top=50;transparent=1;z=7;edge=1;cls="static" };
		 trackbar3={ bgcolor=16711680;bottom=199;max=255;right=278;left=38;top=169;z=4;min=0;cls="trackbar" };
		 static3={ bottom=199;color=0;text="static";left=297;top=171;font=LOGFONT( h=-20 );center=1;z=6;right=332;transparent=1;cls="static" };
		 trackbar2={ bgcolor=65280;bottom=140;max=255;right=278;left=38;top=110;z=3;min=0;cls="trackbar" }
		 )
		 /*}}*/
		 winform.trackbar3.oncommand = function(id,event,pos){
		   select(event) {
		     case 0x0000 ; 0x0005 {
		         b = winform.trackbar3.pos
		         winform.static3.text =b
		         color =r|(g<<8)|(b<<16)
		         winform.static4.text =color
		         winform.edit.bgcolor =color
		         winform.edit.redraw()
		     }
		   }
		 }
		 winform.trackbar2.oncommand = function(id,event,pos){
		   select(event) {
		     case 0x0000 ; 0x0005 {//可以取任意pos值
		       g = winform.trackbar2.pos
		       winform.static2.text =g
		       color =r|(g<<8)|(b<<16)
		       winform.static4.text =color
		       winform.edit.bgcolor =color
		       winform.edit.redraw()
		     }
		   }
		 }
		 winform.trackbar.oncommand = function(id,event,pos){
		   	select(event) {
			     case 0x0000 ; 0x0005 {
			    	 r = winform.trackbar.pos
				     winform.static.text =r
				     color =r|(g<<8)|(b<<16)
				     winform.static4.text =color
				     winform.edit.bgcolor =color
				     winform.edit.redraw()
			    }
			 }
		 }
		 r=winform.trackbar.pos
		 g=winform.trackbar2.pos
		 b=winform.trackbar3.pos
		 winform.static.text=r
		 winform.static2.text =g
		 winform.static3.text =b
		 color =r|(g<<8)|(b<<16)
		 winform.static4.text =color
		 winform.edit.bgcolor =color//不知道那个控件可以动态设置背景颜色，暂时用edit演示，有知道的告诉我一下。
		 /**这段现在可以不用了，因为库已更新了，默认是有滑块。
		 winform.trackbar.modifyStyle(0x80/*_TBS_NOTHUMB*/)
		 winform.trackbar2.modifyStyle(0x80/*_TBS_NOTHUMB*/)
		 winform.trackbar3.modifyStyle(0x80/*_TBS_NOTHUMB*/)
		 **/
		 winform.show() 
		 win.loopMessage();