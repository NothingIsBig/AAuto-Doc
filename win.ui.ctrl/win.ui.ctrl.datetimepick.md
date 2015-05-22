#datetimepick-日期控件


###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>updown</td><td>1/0，滚动按钮，在控件的右边显示滚动按钮</td></tr>
</table>	
###成员
<table>
	<tr><td>time</td><td>获取或设置时间</td></tr>
	<tr><td>setRange(.(时间下限,时间上限)</td><td>设置时间范围,参数为time()对象\n可省略其中一个参数,仅指定下限或仅指定上限</td></tr>
	<tr><td>getRange()</td><td>返回两个time()对象:时间范围下限,时间范围上限\n如果未调用setRange()指定上限或下限,相应值返回为空</td></tr>
	<tr><td>setFormat("'时间'hh':'m':'s ddddMMMdd', 'yyy")</td><td>所有非格式化字符必须包含在单引号中</td></tr>
</table>

##示例
* **日期控件示例**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		 datetimepick={ bottom=123;right=440;left=92;top=103;z=1;edge=1;cls="datetimepick" }
		 )
		/*}}*/
		
		import console;
		 winform.datetimepick.onnotify = function(id,code,ptr){ 		
		     select(code) {
		         case 0xFFFFFD0E/*_DTN_DROPDOWN*/{
		             owner.state = "dropdown"
		         }
		         case 0xFFFFFD0F/*_DTN_CLOSEUP*/ {
		             if( owner.state == "changed" ){
		                 console.log("改变了")
		             }
		             owner.state = "closeup"
		         }
		         case 0xFFFFFD09/*_DTN_DATETIMECHANGE*/ {
		             if( owner.state == "dropdown" ){
		                 owner.state = "changed"
		             }
		             else if( owner.state != "changed" ){
		                 console.log("改变了")
		             }		             
		         } 
		     }
		 }
		 winform.show() 
		 win.loopMessage();