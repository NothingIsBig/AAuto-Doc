#groupbox-组合框

### 成员
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
</table>

##示例

* **重绘groupbox的标题**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( text="AAuto Form";bottom=399;parent=...;right=599 )
		winform.add( 
		groupbox={ bottom=176;color=255;text="测试标题";left=104;top=40;font=LOGFONT( h=-19;name='楷体_GB2312';weight=700;italic=1 );z=1;right=360;edge=1;cls="groupbox" };
		groupbox2={ bottom=368;color=255;right=360;left=104;top=200;font=LOGFONT( h=-19;name='楷体_GB2312';weight=700;italic=1 );z=2;text="测试标题";edge=1;cls="groupbox" }
		)
		/*}}*/

		::GetDCEx = ::User32.api("GetDCEx", "pointer( int hWnd, int hrgnClip, int flags )"); 
		::GetClassLong = ::User32.api("GetClassLong", "int( int hWnd, int nIndex )"); 
		::SetWindowText = ::User32.api("SetWindowTextA","int(int hwnd,string lpString)");
		::GetWindowText = ::User32.api("GetWindowTextA","int(int hwnd,string& lpString,int cch)");

		//获取原来groupbox的标题
		var len,title = ::GetWindowText(winform.groupbox.hwnd,50,50)			
		title = string.left(title,len)

		winform.groupbox.wndproc = function(hwnd,message,wParam,lParam){
			select(message) {
				case 0x85/*_WM_NCPAINT*/ {
					var hDC = ::GetDCEx( hwnd, wParam, 0x1/*_DCX_WINDOW*/ | 0x80/*_DCX_INTERSECTRGN*/ )
					if(!hDC){
						hDC = ::GetWindowDC(hwnd)
					}
					//清除原来的标题
					::SetWindowText(hwnd,"")
					//设置设备环境的字体颜色
					::SetTextColor( hDC, 0x0000ff)
					//设置背景			
					::SetBkColor(hDC,0xd8e9ec)
					//::SetBkMode(hDC,0x1/*_TRANSPARENT*/)			
					//获取groupbox的字体结构体
					var hFont = ::CreateFontIndirect(winform.groupbox.getFont())
					//选择对象到设备环境
					::SelectObject( hDC, hFont );
					//输出文字
					::TextOut(hDC,5,0,title,#title)
					//删除对象
					::DeleteObject( hFont )			
					//是否设备环境
					::ReleaseDC( hwnd, hDC )			
					return  1; 			
				}
				
			}	
		}
		winform.show() 
		win.loopMessage();
