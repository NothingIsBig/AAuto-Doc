##示例

* **hotkey控件示例**
	
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

* **热键注册**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="按键注册热键实例";right=263;bottom=87 )
		winform.add( 
		button={ bottom=56;right=192;left=48;top=24;font=LOGFONT( name="宋体";h=-12 );z=1;text="按键(Ctrl+X)";cls="button" }
		)
		/*}}*/		
		hkid = winform.reghotkey(function(id,mod,vk){		
		    winform.button.oncommand( )		
		}
		,0x2/*_MOD_CONTROL*/,'X'#);		
		winform.button.oncommand = function(id,event){
		    //win.msgbox( winform.button.text );
		    win.msgbox("按键被点击了","AAuto")		    
		}		
		winform.show() 
		win.loopMessage();