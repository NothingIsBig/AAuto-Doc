#progress-进度条控件


###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>min</td><td>number，最小值</td></tr>
	<tr><td>max</td><td>number，最大值</td></tr>
</table>

###成员
<table>
<tr><td>delta(偏移值)</td><td>修改当前进度,参数指定相对于当前进度的偏移值</td></tr>
<tr><td>stepIt()</td><td>进度条前进一个增量,返回步进前位置</td></tr>
<tr><td>step</td><td>设置stepIt()函数的步进增量,默认为10</td></tr>
<tr><td>pos</td><td>进度条位置</td></tr>
<tr><td>setRange(最小值,最大值)</td><td>设置进度条最大值,最小值</td></tr>
<tr><td>max</td><td>最大值</td></tr>
<tr><td>min</td><td>最小值</td></tr>
</table>
##示例
* **进度条示例**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		progress1={ bottom=58;max=100;text="progress";left=21;top=38;font=LOGFONT( name="宋体";h=-12 );z=1;right=308;min=0;edge=1;cls="progress" };
		button={ bottom=163;text="button";left=106;top=138;font=LOGFONT( name="宋体";h=-12 );z=2;right=219;cls="button" }
		)
		/*}}*/		
		winform.button.oncommand = function(id,event){		
		    ret = win.invoke(
		        function(hwnd){ 
		            import win.ui;
		            var progress1 = win.ui.ctrl.progress(,{} ); 
		            progress1.hwnd = hwnd
		            for(i=1;100){
		                progress1.pos = i
		                sleep(50) 
		            } 
		        },winform.progress1.hwnd
		    )		    
		}		
		winform.show() 
		win.loopMessage();
		return winform;

* 进度条示例二

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=105;parent=...;right=555;text="AAuto Form" )
		 winform.add( 
		 progress={ bottom=61;max=100;right=341;left=36;top=47;z=1;hide=1;min=0;edge=1;cls="progress" };
		 button={ bottom=72;text="点这里测试滚动条";left=374;top=40;z=2;right=504;cls="button" }
		 )
		/*}}*/
		
		 winform.button.oncommand = function(id,event){
		     winform.progress.hide = false;
		     winform.progress.max = 100;		     
		     for(i=1;100;1){
		         winform.progress.pos = i; 
		         win.delay(10)
		     }		     
		     winform.progress.hide = true;
		     winform.msgbox("已完成")
		 }		
		 winform.show() 
		 win.loopMessage();