#scrollbar-滚动条控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>horz</td><td>1/0，显示方向，0：垂直，1：水平</td></tr>
</table>
###成员
<table>
	<tr><td>pos</td><td>获取或设置滚动按钮的当前位置,如果赋值为负数、可禁止窗口重绘</td></tr>
	<tr><td>setRange(1,100)</td><td>设置滚动条范围</td></tr>
	<tr><td>getRange()</td><td>返回两个数值,表示滚动条范围 </td></tr>
	<tr><td>enable( _ESB___ )</td><td>激活一个或两个滚动条箭头或是使其失效</td></tr>
</table>

##示例
* **拖动scrollbar改变edit的text**

		import win.ui;
				
		/*DSG{{*/
		var winform = ..win.form( text="滚动条";bottom=203;parent=...;right=438;max=false )
		winform.add( 
		scrollbar={ dl=1;bottom=114;max=100;horz=1;left=141;top=89;z=1;db=1;right=375;min=1;cls="scrollbar" };
		editScrollbar={ left=46;dl=1;bottom=114;text="1";readonly=1;multiline=1;top=89;right=119;z=2;db=1;edge=1;cls="edit" }
		)
		/*}}*/

		winform.scrollbar.setRange(1,100)
		winform.scrollbar.enable(0x0/*_ESB_ENABLE_BOTH*/)
		winform.scrollbar.oncommand = function(id,event,pos){
				select(event) {
				    case 0x0 {
				        winform.scrollbar.pos--
				        winform.editScrollbar.text =winform.scrollbar.pos
				    }
				    case 0x1 {
				        winform.scrollbar.pos++
				        winform.editScrollbar.text =winform.scrollbar.pos 
				    }
				    case 0x5 {
				        winform.editScrollbar.text = pos 
				        winform.scrollbar.pos = pos; 
				    }
				} 
		}
		winform.show() 
		win.loopMessage();