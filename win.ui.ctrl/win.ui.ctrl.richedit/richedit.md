# richedit

### 类名 : richedit
### 命名空间 : win.ui.ctrl


##成员


## 示例 
* 富文本框自定义右键菜单

		import win.ui;
		import win.ui.menu;
		/*DSG{{*/
		var winform = win.form(parent=...; min=1;bottom=249;max=false;text="AAuto Form";right=349 )
		winform.add( 
		richedit={ bottom=230;right=338;left=11;multiline=1;top=43;font=LOGFONT( name="宋体";h=-12 );vscroll=1;z=1;text="richedit";hscroll=1;edge=1;cls="richedit" }
		)
		/*}}*/		
		winform.popmenu = win.ui.popmenu(winform);//创建弹出菜单
		winform.popmenu.add('全选(&A)',function(id){
			//在下面输入菜单响应代码
		});
		winform.popmenu.add();//分隔线
		winform.popmenu.add('从右到左的阅读顺序(&R)',function(id){
			//在下面输入菜单响应代码
			if (winform.popmenu.checked(3)) {
				winform.popmenu.check(3,false);
				win.msgbox("取消选中菜单项");
			} else {
				winform.popmenu.check(3);
				win.msgbox("选中菜单项");
			}
		});		
		//richedit 消息回调
		winform.richedit.wndproc = function(hwnd,message,wparam,lparam){
			if(message == 0x205) {
				import mouse;
				var x,y = mouse.getPos();
				winform.popmenu.popup(x,y,true);//弹出菜单
				//winform.popmenu.popup(::LOWORD(lparam), ::HIWORD(lparam));//弹出菜单
			}
		}		
		winform.show() 
		win.loopMessage();
		return winform;
		
* **RichEdit与Edit连动**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="AAuto Form";right=349;bottom=249 )
		winform.add( 
		richedit={ bottom=74;color=0;right=300;left=46;multiline=1;top=18;font=LOGFONT( name="Microsoft Sans Serif";h=-12;out=3;family=34;clip=2;quality=1 );z=1;text="";edge=1;cls="richedit" };
		edit={ bottom=177;right=300;left=46;multiline=1;top=121;z=2;text="";edge=1;cls="edit" }
		)
		/*}}*/		
		//如果经接收_EN_CHANGE通知就要加下面这句
		winform.richedit.modifyEvent(,0x1/*_ENM_CHANGE*/)
		
		winform.richedit.oncommand = function(id,event){
		    if(event == 0x300/*_EN_CHANGE*/){
		        //文本发生改变了
		        winform.edit.text = winform.richedit.text
		    } 
		}
		
		winform.show() 
		win.loopMessage();