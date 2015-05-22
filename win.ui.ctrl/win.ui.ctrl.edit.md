#edit-文本框控件

### 设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
	<tr><td>hscroll</td><td>1/0，是否显示横向滚动条</td></tr>
	<tr><td>vscroll</td><td>1/0，是否显示垂直垂直滚动</td></tr>
	<tr><td>multiline</td><td>1/0，文本是否支持换行，开启换行以及纵向自动滚动则支持文本自动换行</td></tr>
	<tr><td>autohscroll</td><td>1/0，输入超出高度时是否自动向下滚动，如需自动换行必须启用该属性</td></tr>
	<tr><td>autovscroll</td><td>1/0，输入超出宽度时是否自动向右滚动，启用该属性自动换行失效</td></tr>
	<tr><td>readonly</td><td>1/0，文本只读（变灰色）</td></tr>
	<tr><td>password</td><td>1/0，将输入文本显示为星号</td></tr>
	<tr><td>num</td><td>1/0，仅允许输入数字</td></tr>
	<tr><td>hidesel</td><td>1/0，当文本框失去焦点时，是否取消选区</td></tr>
</table>


###成员
<table>
	<tr><td>text</td><td>编辑控件文本属性</td></tr>
	<tr><td>modified</td><td>文本内容是否已修改 </td></tr>
	<tr><td>limit</td><td>字符数限制</td></tr>
	<tr><td>lineCount</td><td>获取行数</td></tr>
	<tr><td>appendText(追加文本)</td><td>追加文本并移动光标到文本尾部,支持零个、或多个参数,参数使用tostring()转换为文本,返回文本总长度</td></tr>
	<tr><td>selText</td><td>获取或替换选区文本</td></tr>	
	<tr><td>setsel(1,__)</td><td>设置选区,参数(起始位置,结束位置)</td></tr>
	<tr><td>getsel()</td><td>获取选区起始位置,结束位置 </td></tr>
	<tr><td>deselect()</td><td>取消选定 </td></tr>
	<tr><td>selectAll()</td><td>全选</td></tr>
	<tr><td>lineToChar(__/*指定行号*/)</td><td>获取指定行首字符偏移位置</td></tr>
	<tr><td>lineToChar()</td><td>获取当前选定行首字符偏移位置</td></tr>
	<tr><td>lineFromChar(__/*指定位置*/)</td><td>返回指定位置行数</td></tr>
	<tr><td>lineFromChar()</td><td>不指定参数则返回当前行</td></tr>
	<tr><td>lineLength(__/*指定行号*/)</td><td>返回指定行字符数</td></tr>
	<tr><td>lineLength()</td><td>不指定行号参数,则获取当前行字符数</td></tr>
	<tr><td>lineText(__/*指定行号*/)</td><td>获取指定行文本</td></tr>
	<tr><td>lineText()</td><td>不指定行号参数,则获取当前行文本</td></tr>
	<tr><td>setFocus(</td><td> 设置焦点，可指定选区参数</td></tr>
	<tr><td>setFocus()</td><td>设置焦点到文本框尾部</td></tr>
	<tr><td>setFocus(0)</td><td>设置焦点到文本框的指定位置</td></tr>
	<tr><td>setFocus(0,-1)</td><td>全选并设置焦点</td></tr>
	<tr><td>scrollCaret()</td><td>滚动到光标处</td></tr>
	<tr><td>lineScroll(滚动到指定行)</td><td>滚动条移动到指定行,如果不指定参数则滚动到最后一行 </td></tr>
	<tr><td>vScroll()</td><td>滚动到底部</td></tr>
	<tr><td>hScroll()</td><td>滚动到右侧</td></tr>
	<tr><td>vScroll(_SB__)</td><td>滚动竖向滚动条</td></tr>
	<tr><td>hScroll(_SB__)</td><td>滚动横向滚动条</td></tr>
	<tr><td>redo()</td><td>重做</td></tr>
	<tr><td>undo()</td><td>撤消</td></tr>
	<tr><td>clear()</td><td>清除选中文本</td></tr>
	<tr><td>copy()</td><td>复制</td></tr>
	<tr><td>cut()</td><td>剪切</td></tr>
	<tr><td>paste()</td><td>粘贴</td></tr>
	<tr><td>canRedo()</td><td>能否重做</td></tr>
	<tr><td>canUndo()</td><td>能否撤消</td></tr>
	<tr><td>canPaste()</td><td>能否粘贴</td></tr>
	<tr><td>canCopy()</td><td>能否复制</td></tr>
</table>

####注意  
* 当多行为true时，Tab键失效
* 设置Tab控制为true，切换顺序为z值
* 自动换行要设置多行为true，并增加style=1539



## 示例
* **设置edit控件自动换行**

				//设置style=1539和multiline=1
		edit={ bottom=191;right=304;left=32;multiline=1;top=20;font=LOGFONT( name="宋体";h=-12 );multiline=1;style=1539;z=1;vscroll=1;text="edit";edge=1;cls="edit" }

* **多行edit响应Tab键**
	

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=768;parent=...;text="网站自动刷新1.0";right=1024;scroll=1 )
		winform.add( 
		btnDX={ bottom=220;color=0;text="电信接口";left=20;top=180;font=LOGFONT( name='微软雅黑';h=-16 );z=4;right=507;tabstop=1;cls="button" };
		edit={ dr=1;dl=1;bottom=170;tabstop=1;right=850;left=20;multiline=1;top=20;font=LOGFONT( name='微软雅黑';h=-16 );style=1539;z=1;vscroll=1;edge=1;cls="edit" };
		id={ tabstop=1;bottom=50;right=1004;left=870;top=20;font=LOGFONT( name='微软雅黑';h=-16 );z=2;edge=1;cls="edit" };
		btnWT={ bottom=220;color=0;text="网通接口";left=517;top=180;font=LOGFONT( name='微软雅黑';h=-16 );z=5;right=1004;tabstop=1;cls="button" };
		VerifyCode={ z=3;bottom=90;right=1004;left=870;top=60;font=LOGFONT( name='微软雅黑';h=-16 );tabstop=1;edge=1;cls="edit" }
		)
		/*}}*/

		winform.show();
		winform.edit.setFocus(); 
		//多行文本框是不支持tab切换的，自已处理按键消息就可以了
		winform.edit.wndproc = function(hwnd,message,wParam,lParam){
		    if( message == 0x100/*_WM_KEYDOWN*/ ){
		        if( wParam == 0x9/*_VK_TAB*/ ){
		            win.setFocus( win.GetWindow( winform.edit.hwnd,0x2/*_GW_HWNDNEXT*/ ) )
		            return false;//禁止默认消息处理
		        }
		    }
		}
		win.loopMessage();
		return winform,wb;

* **文本框注册回车键回车后执行其他代码**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 		
		edit={ bottom=75;right=260;left=84;top=38;font=LOGFONT( name="宋体";h=-12 );z=1;text="edit";edge=1;cls="edit" }
		)
		/*}}*/
		
		winform.edit.wndproc = function(hwnd,message,wparam,lparam){
		        if (message == 0x101/*_WM_KEYUP*/ && wparam == 13/*释放回车键*/) {
		                winform.msgbox(winform.edit.text);
		        }
		        //无返回值则继续调用默认回调函数
		}
		winform.show() 
		win.loopMessage();
		return winform;

* **文本框限制只输入16进制数**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		edit={ bottom=65;right=307;left=48;multiline=1;top=38;z=1;text="";edge=1;cls="edit" }
		)
		/*}}*/	
		winform.edit.oncommand = function(id,event){	
		    if(  event == 0x300/*_EN_CHANGE*/ ){ 	    
		        var text = winform.edit.text;
		        var text2 = string.replace(  text,"[^0-9A-F ]","");	        
		        if( text2 != text ){	        
		            winform.edit.text = text2;	            
		            import win.util.tray;
		            win.util.tray.pop("除0-9，A-F和空格外不能输入其它字符","输入错误")
		            winform.edit.setFocus();
		            winform.edit.setsel(#text2,#text2);
		        }
		    } 
		}	
		winform.show() 
		win.loopMessage();
* **文本框限制只能输入数字,小数点及-号**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		edit={ bottom=128;right=256;left=88;top=104;font=LOGFONT( name="宋体";h=-12 );z=1;text="";edge=1;cls="edit" }
		)
		/*}}*/
		//监视传递给edit的所有消息，并针对需要干预的情况做处理
		winform.edit.wndproc = function(hwnd,message,wParam,lParam){
		//如果有_WM_CHAR消息传给edit
		    if (message == 0x102/*_WM_CHAR*/) {
		   //如果字符的ASCII码大于等于0或等于小于9
		        if (wParam >= '0'# && wParam <= '9'#) {
		        //返回空，即按系统默认的方法继续（不干预系统的正常流程）
		            return;
		        }
		        //选择wParam参数，针对它的不同值处理
		        select wParam {
		        //为"-"的ASC码的时候
		            case '-'# {
		            //如果edit控件中没有任何字符，-只能在最前面
		                if (#winform.edit.text == 0)
		                        //返回空，即按系统默认的方法继续（不干预系统的正常流程）
		                    return;
		            }
		            case '.'# {
		                        //如果edit控件中匹配不到小数点并且能匹配到数字（因为小数点只能有一个并且必须跟在数字后面）
		                if ( ! string.match(winform.edit.text, "\.") and string.match(winform.edit.text, "\d"))
		                    return;
		            }		            
		           //对于删除键，等控制键不干预不处理 
		            case 0x8/*_VK_BACK*/, 0xD/*_VK_RETURN*/, 0x2E/*_VK_DELETE*/ {
		                return;
		            }
		        }
		        //其它字符录入一概阻断
		        return 1;
		    }
		}
		winform.show();
		win.loopMessage();

	_封装成自定义控件_

		import win.ui;
		//begin封装
		import win.mm;
		import win.ui.ctrl.edit;
		namespace win.ui.ctrl {
		    numberedit = class {
		        ctor (parent, tvalue) {
		            tvalue.cls = "edit";
		            this = ..win.ui.ctrl.edit(parent, tvalue);
		        }		        
		        onCreate = function () {
		            this.wndproc = function(hwnd,message,wParam,lParam){
		                if (message == 0x102/*_WM_CHAR*/) {
		                    if (wParam >= '0'# && wParam <= '9'#) {
		                        return;
		                    }
		                    select wParam {
		                        case '-'# {
		                            if (::SendMessage(this.hwnd, 0xE/*_WM_GETTEXTLENGTH*/) == 0)
		                                return;
		                        }
		                        case '.'# {
		                            if ( ! ..string.match(this.text, "\."))
		                                return;
		                        }
		                        case 0x8/*_VK_BACK*/, 0xD/*_VK_RETURN*/, 0x2E/*_VK_DELETE*/ {
		                            return;
		                        }
		                    }
		                    ..win.mm.msgBeep();
		                    return 1;
		                }
		            }
		        }
		    }
		}
		//end封装		
		/*DSG{{*/
		var winform = win.form(parent=...; right=191;bottom=151;max=false;text="AAuto Form";border="dialog frame" )
		winform.add( 
		numberedit={ hidesel=1;text="1.0";bottom=40;right=168;left=24;z=1;top=16;font=LOGFONT( name="宋体";h=-12 );tabstop=1;edge=1;cls="numberedit" };
		numberedit4={ hidesel=1;text="4.5";bottom=136;right=168;left=24;z=4;top=112;font=LOGFONT( name="宋体";h=-12 );tabstop=1;edge=1;cls="numberedit" };
		numberedit3={ hidesel=1;text="3";bottom=104;right=168;left=24;z=3;top=80;font=LOGFONT( name="宋体";h=-12 );tabstop=1;edge=1;cls="numberedit" };
		numberedit2={ hidesel=1;text="1.5";bottom=72;right=168;left=24;z=2;top=48;font=LOGFONT( name="宋体";h=-12 );tabstop=1;edge=1;cls="numberedit" }
		)
		/*}}*/		
		winform.show();
		win.loopMessage();

* **三个edit控件联动**

	如果没有multiline=1会发现错误,原因我暂时不明

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
			static3={ bottom=116;right=465;left=369;text="分米";top=77;z=6;transparent=1;cls="static" };
			edit={ text="10";num=1;bottom=177;right=174;left=37;multiline=1;top=119;z=1;edge=1;cls="edit" };
			static2={ bottom=116;right=295;left=202;text="厘米";top=77;z=5;transparent=1;cls="static" };
			static={ bottom=116;right=128;left=35;text="毫米";top=77;z=4;transparent=1;cls="static" };
			edit3={ num=1;bottom=177;right=503;left=366;multiline=1;top=119;z=3;edge=1;cls="edit" };
			edit2={ num=1;bottom=177;right=338;left=202;multiline=1;top=119;z=2;edge=1;cls="edit" }
		)
		/*}}*/
		winform.edit3.oncommand = function(id,event){
			//winform.msgbox( winform.edit3.text );
			if(event =0x300/*_EN_CHANGE*/){
				winform.edit.text = winform.edit3.text * 100 ; 
				winform.edit2.text = winform.edit3.text * 10 ; 
			} 
		}
		winform.edit2.oncommand = function(id,event){
			//winform.msgbox( winform.edit2.text );
			if(event =0x300/*_EN_CHANGE*/){
				winform.edit3.text = winform.edit2.text / 10 ; 
				winform.edit.text = winform.edit2.text * 10 ; 
			} 
		}
		winform.wndproc = function(hwnd,message,wParam,lParam){
			select( message ) { 
				case 0x205/*_WM_RBUTTONUP*/{
					//鼠标右键弹起,下面获取坐标
					var x,y = win.getMessagePos(lParam);
				}
				else{
				}
			}
			//无返回值则继续调用默认回调函数
		}
		winform.edit.oncommand = function(id,event){
			if(event =0x300/*_EN_CHANGE*/){
				winform.edit2.text = winform.edit.text * 10 ; 
				winform.edit3.text = winform.edit.text * 100 ; 
			} 
		}
		winform.show() 
		win.loopMessage();


* **IP地址输入框**

		import win.ui;
		namespace win.ui.ctrl {
		    ipedit = class {
		        ctor (parent, tvalue) {
		            tvalue.cls = "SysIPAddress32";
		        }
		        @_metaProperty;
		    }
		    ipedit._metaProperty = edit._metaProperty;
		}
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		button={ bottom=168;right=384;left=320;top=144;z=2;text="button";cls="button" };
		ipedit={ bottom=168;text="custom";left=152;autosize=1;top=144;center=1;z=1;right=312;transparent=1;edge=1;cls="ipedit" }
		)
		/*}}*/

		winform.ipedit.text = "127.0.0.1";

		winform.button.oncommand = function (id,event) {
		    winform.msgbox(winform.ipedit.text);
		}

		winform.show();
		win.loopMessage();

* **拖放多个文件到edit控件**


		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( right=610;bottom=351;topmost=1;text="拖放文件";parent=...)
		winform.add( 
		edit={ bottom=318;right=582;left=30;multiline=1;top=42;acceptfiles=1;z=1;text="把外部文件拖放到这里";edge=1;cls="edit" }
		)
		/*}}*/

		winform.edit.wndproc = {
		    [0x233/*_WM_DROPFILES*/] = function(hwnd,message,wParam,lParam){ 
		        var dropFiles = win.getDropFile(wParam) 
		        winform.edit.text = string.join(dropFiles,'\r\n'); 
		        // 可用io.splitpath解析文件名和路径等信息
		   }
		}
		winform.show() 
		win.loopMessage();

* **动态设置edit的readonly**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=186;parent=...;right=278;text="动态设置编辑框只读" )
		winform.add( 
		btn_restore={ bottom=138;right=234;left=161;top=106;z=3;text="还原";cls="button" };
		btn_setReadOnly={ bottom=138;right=114;left=41;top=106;z=2;text="设置只读";cls="button" };
		edit={ bottom=76;right=240;left=37;top=51;z=1;edge=1;cls="edit" }
		)
		/*}}*/

		winform.btn_restore.oncommand = function(id,event){
			::PostMessage(winform.edit.hwnd,0xCF/*_EM_SETREADONLY*/,0,0);
		}

		winform.btn_setReadOnly.oncommand = function(id,event){
			::PostMessage(winform.edit.hwnd,0xCF/*_EM_SETREADONLY*/,1,0);
		}

		winform.show() 
		win.loopMessage();

* **用方向键切换不同edit**

		import win.ui;
		import key.hotkey;
		/*DSG{{*/
		var winform = ..win.form( bottom=257;parent=...;text="AAuto Form";right=555 )
		winform.add( 
		edit4={ right=171;bottom=105;text="edit4";left=27;top=72;z=4;edge=1;cls="edit" };
		edit5={ right=329;bottom=105;text="edit5";left=185;top=72;z=5;edge=1;cls="edit" };
		edit12={ right=483;bottom=189;text="edit12";left=339;top=156;z=12;edge=1;cls="edit" };
		edit7={ right=170;bottom=147;text="edit7";left=26;top=114;z=7;edge=1;cls="edit" };
		edit8={ right=328;bottom=147;text="edit8";left=184;top=114;z=8;edge=1;cls="edit" };
		edit11={ right=327;bottom=190;text="edit11";left=183;top=157;z=11;edge=1;cls="edit" };
		edit9={ right=484;bottom=146;text="edit9";left=340;top=113;z=9;edge=1;cls="edit" };
		edit3={ right=484;bottom=58;text="edit3";left=340;top=25;z=3;edge=1;cls="edit" };
		edit10={ right=169;bottom=190;text="edit10";left=25;top=157;z=10;edge=1;cls="edit" };
		edit6={ right=485;bottom=104;text="edit6";left=341;top=71;z=6;edge=1;cls="edit" };
		edit1={ text="edit1";bottom=59;right=170;left=26;top=26;z=1;edge=1;cls="edit" };
		edit2={ right=328;bottom=59;text="edit2";left=184;top=26;z=2;edge=1;cls="edit" }
		)
		/*}}*/

		hotkey = key.hotkey(winform) 
		current=1//默认选择第一个edit1
		winform["edit"+current].setFocus(tonumber(winform["edit"+current].text))

		hotkey.reg(
		    "LEFT",
		    function(hwnd,...){
		         if current!=1{current=current-1;winform["edit"+current].setFocus(tonumber(winform["edit"+current].text))  }     
		    } 
		 )
		hotkey.reg(
		    "RIGHT",
		    function(hwnd,...){
		         if current!=12{current=current+1;winform["edit"+current].setFocus(tonumber(winform["edit"+current].text))  }     
		    } 
		 )
		 hotkey.reg(
		    "UP",
		    function(hwnd,...){
		         if current>3{current=current-3;winform["edit"+current].setFocus(tonumber(winform["edit"+current].text))  }     
		    } 
		 )
		 hotkey.reg(
		    "DOWN",
		    function(hwnd,...){
		         if current<10{current=current+3;winform["edit"+current].setFocus(tonumber(winform["edit"+current].text))  }     
		    } 
		 )

		winform.show() 
		win.loopMessage();

* **edit内输入Tab键**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
		edit={ bottom=244;text="edit";left=92;multiline=1;top=42;z=1;right=450;edge=1;cls="edit" }
		)
		/*}}*/
		winform.edit.translateAccelerator = function(msg){
		    __messageTranslateDispatch(msg)
		    return true;
		}
		winform.show() 
		win.loopMessage();