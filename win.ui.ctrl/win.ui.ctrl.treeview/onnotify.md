

##示例
* **检测treeview控件上的点击事件**

		import win.ui;
		/*DSG{{*/
		var winform = win.form(parent=...; text="树形控件 - 判断点击位置";right=349;bottom=249 )
		winform.add( 
		treeview={ bgcolor=15793151;bottom=190;asel=false;right=326;left=22;text="treeview";top=17;style=256;z=1;cls="treeview";editable=1;edge=1;exstyle=131072 }
		)
		/*}}*/		
		winform.treeview.insertItem( { 
		        text = "父节点"; 
		        children = { 
		            { text = "子节点"  };
		            { text = "子节点2" };
		        }
		} )		
		io.open()
		import mouse;
		winform.treeview.onnotify = function(id,code,ptr){
		     if( code = 0xFFFFFFFE/*_NM_CLICK*/ ){  
		        var x,y = mouse.getPos();
		        var hitem,ht = winform.treeview.hitTest(x,y,true)
		        select(ht) {
		            case 4/*_TVHT_ONITEMLABEL*/   {
		                ..io.print("你点在文本上了")
		            }
		            case 0x40/*_TVHT_ONITEMSTATEICON*/ {
		                ..io.print("你点在状态图标上了")
		            }
		            case 8/*_TVHT_ONITEMINDENT*/  {
		                ..io.print("你点在缩进部分了")
		            }
		            case 2/*_TVHT_ONITEMICON*/   {
		                ..io.print("你点在图标上了")
		            }
		            case 0x40/*_TVHT_ONITEMSTATEICON*/    {
		                ..io.print("你点在状态图标上了")
		            }
		            case 0x10/*_TVHT_ONITEMBUTTON*/    {
		                ..io.print("你点在项目按钮上了")
		            }
		            else {
		                ..io.print("你点在空白部份了")
		            }
		        }
		     } 
		}		    
		winform.show() 
		win.loopMessage();