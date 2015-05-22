#calendar-日历控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
</table>

###成员
<table>
	<tr><td>time</td><td>获取或设置时间</td></tr>
	<tr><td>setRange(时间下限,时间上限)</td><td>设置时间范围,参数为time()对象,可省略其中一个参数,仅指定下限或仅指定上限</td></tr>
	<tr><td>getRange()</td><td>返回两个time()对象:时间范围下限,时间范围上限,如果未调用setRange()指定上限或下限,相应值返回为空</td></tr>
</table>
