#richedit-多功能文本框

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
</table>

###成员
<table>
	<tr><td>text</td><td>编辑控件文本属性</td></tr>
	<tr><td>lineCount</td><td>获取行数</td></tr>
	<tr><td>limit</td><td>字符数限制</td></tr>
	<tr><td>modified</td><td>文本内容是否已修改</td></tr>
	<tr><td>wrap</td><td>是否启用自动换行，仅richedit支持</td></tr>
	<tr><td>modifyEvent(移除通知,添加通知)</td><td>启用或禁用通知消息,返回EVENTMASK值</td></tr>
	<tr><td>setsel(1,__)</td><td>设置选区,参数(起始位置,结束位置)</td></tr>
	<tr><td>getsel()</td><td>获取选区起始位置,结束位置</td></tr>
	<tr><td>selText</td><td>获取或设置选区文本</td></tr>
	<tr><td>deselect()</td><td>取消选定 </td></tr>
	<tr><td>rangeText(起始位置,结束位置)</td><td>返回指定位置文本</td></tr>
	<tr><td>appendText(追加文本)</td><td>追加文本并移动光标到文本尾部,支持零个、或多个文本参数,返回文本总长度</td></tr>
	<tr><td>lineScroll(滚动到指定行)</td><td>滚动条移动到指定行,如果不指定参数则滚动到最后一行 </td></tr>
	<tr><td>lineToChar(__/*指定行号*/)</td><td>获取指定行首字符偏移位置</td></tr>
	<tr><td>lineToChar()</td><td>获取当前选定行首字符偏移位置</td></tr>
	<tr><td>lineFromChar(__/*指定位置*/)</td><td>返回指定位置行数</td></tr>
	<tr><td>lineFromChar()</td><td>不指定参数则返回当前行</td></tr>
	<tr><td>lineText(__/*指定行号*/)</td><td>获取指定行文本</td></tr>
	<tr><td>lineText()</td><td>不指定行号参数,则获取当前行文本 </td></tr>
	<tr><td>lineLength(__/*指定行号*/)</td><td>返回指定行字符数</td></tr>
	<tr><td>lineLength()</td><td>不指定行号参数,则获取当前行字符数</td></tr>
	<tr><td>onlink</td><td>@.onlink=function(msg,title){,	,}</td></tr>
	<tr><td>setFocus()</td><td>设置焦点 </td></tr>
	<tr><td>scrollCaret</td><td>滚动到光标处</td></tr>
	<tr><td>vScroll()</td><td>滚动到底部</td></tr>
	<tr><td>hScroll()</td><td>滚动到右侧</td></tr>
	<tr><td>vScroll(_SB__)</td><td>滚动竖向滚动条</td></tr>
	<tr><td>hScroll(_SB__)</td><td>滚动横向滚动条</td></tr>
	<tr><td>selectAll()</td><td>全选</td></tr>
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

##示例
* **让richedit的滚动条始终保持在最下面**

			import win.ui;
			/*DSG{{*/
			var winform = ..win.form( bottom=191;parent=...;text="AAuto Form";right=263 )
			winform.add( 
			richedit={ bottom=160;vscroll=1;wrap=1;left=45;multiline=1;top=20;text="richeditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditricheditrichedit";z=1;right=210;hscroll=1;edge=1;cls="richedit" }
			)
			/*}}*/
			winform.richedit.setsel(-1,-1) //最后一行在富文本框最下
			winform.richedit.lineScroll( winform.lineCount ) //最后一行在富文本框最上
			winform.show() 
			win.loopMessage();

* **richedit的右键菜单**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=249;parent=...;right=349;text="AAuto Form" )
		winform.add( 
		richedit={ bottom=170;right=211;left=71;multiline=1;top=62;font=LOGFONT( name='宋体' );z=1;text="richedit";edge=1;cls="richedit" }
		)
		/*}}*/
		import win.ui.menu;
		import mouse;
		winform.popmenu = win.ui.popmenu(winform);//创建弹出菜单
		winform.popmenu.add('剪切',function(id){
		   winform.richedit.cut();
		});
		winform.popmenu.add("复制",function(id){
		    winform.richedit.copy();
		});
		winform.popmenu.add("粘贴",function(id){
		   winform.richedit.paste();
		});
		winform.popmenu.add("删除",function(id){
		    winform.richedit.selText = ""
		});
		winform.popmenu.add("全部选择",function(id){
		    winform.richedit.selectAll();
		});
		winform.richedit.wndproc = function(hwnd,message,wparam,lparam){
		    select(message) {//判断消息类型
		        case 0x205/*_WM_RBUTTONUP 鼠标右键弹起，弹出菜单*/begin
		            var x,y = mouse.getPos()
		            if(win.clip.read() == ""){
		                winform.popmenu.enable(3,false)
		            }
		            else {
		                winform.popmenu.enable(3)
		            }
		            if(winform.richedit.selText == null || winform.richedit.selText == ""){
		                winform.popmenu.enable(1,false)
		                winform.popmenu.enable(2,false)
		                winform.popmenu.enable(4,false)
		            }
		            else {
		                winform.popmenu.enable(1)
		                winform.popmenu.enable(2)
		                winform.popmenu.enable(4)
		            }
		            winform.popmenu.popup(x,y,true);//弹出菜单
		        end
		        else{
		        }
		    }
		}
		winform.show() 
		win.loopMessage();
