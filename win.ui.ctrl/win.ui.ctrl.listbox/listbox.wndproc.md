

##示例
* **自绘listbox**

		import win.ui;
		import win.graphics;
		/*DSG{{*/
		var winform = ..win.form( right=472;bottom=344;parent=...;text="AAuto Form";border="resizable" )
		winform.add( 
		listbox={ dr=1;dl=1;bgcolor=16777215;vscroll=1;right=458;left=12;dt=1;db=1;cls="listbox";bottom=332;
		items={  };font=LOGFONT( name='宋体' );style=96;z=1;top=11 }
		)
		/*}}*/
		
		winform.wndproc = function (hwnd,message,wparam,lparam){
		    select(message) {
		        case 0x2C/*_WM_MEASUREITEM*/ {
		            var m = ::MEASUREITEMSTRUCT();
		            raw.convert(topointer(lparam), m);
		            m.itemHeight = 51; // 每个 Item 高 51 个像素
		            ::CopyMemoryByStruct(topointer(lparam), m, raw.sizeof(m));
		        }
		        case 0x2B/*_WM_DRAWITEM*/ {
		            var ds = ::DRAWITEMSTRUCT();
		            raw.convert(topointer(lparam), ds);
		            if (ds.hwndItem == winform.listbox.hwnd) {
		                var cvs = win.graphics.canvas(); // 创建一个画布
		                cvs.fromHDC(ds.hDC); // 传入 hDC
		                cvs.brush.color = 0xffffff; // 定义刷子颜色
		                cvs.fillRect(ds.rcItem);
		                if (ds.itemID > 0) { // 除了第一个 Item，其他的都画线
		                    cvs.pen.color = 0xebebeb; // 定义画笔的颜色
		                    cvs.moveTo(ds.rcItem.left, ds.rcItem.top); // 想像画画的过程，落笔
		                    cvs.lineTo(ds.rcItem.right, ds.rcItem.top); // 提笔
		                }
		                if (ds.itemState & 0x1/*_ODS_SELECTED*/) { // 选中 Item 的绘制
		                    cvs.brush.color = 0xaeebff;
		                    cvs.frameRect(ds.rcItem); // 边框
		                    var rect = ::RECT(ds.rcItem.left + 1, ds.rcItem.top + 1, ds.rcItem.right - 1, ds.rcItem.bottom - 1);
		                    // 结构体在 AAuto 中传递的是内存地址，所以重新构造一个 ::RECT
		                    cvs.brush.color = 0xedfcff;
		                    cvs.frameRect(rect); // 内边框
		                    rect.left++; rect.top++; rect.right--; rect.bottom--;
		                    cvs.gradientFill(rect, 0xddf8fe, 0xb7edff, 0x1/*_GRADIENT_FILL_RECT_V*/);
		                }
		                var data = string.split(winform.listbox.getItemText(ds.itemID + 1), "|");
		                if (#data == 2) {
		                    cvs.font.bold = true; // 粗体
		                    cvs.font.color = 0x000000; // 颜色
		                    cvs.textOut(ds.rcItem.left + 18, ds.rcItem.top + 10, data[1]);
		                    cvs.font.bold = false;
		                    cvs.font.color = 0x666666;
		                    cvs.textOut(ds.rcItem.left + 18, ds.rcItem.top + 26, data[2]);
		                }
		                cvs.destroy();
		            }
		            return 1;
		        }
		    }
		}		
		winform.listbox.add("腾讯QQ|一款及时聊天软件");
		winform.listbox.add("Microsoft Office|一款办公套装");		
		winform.show();
		win.loopMessage();
		