
<table>
	<caption>Edit编辑控件(编辑框)通知消息</caption>
	<tr><td>_EN_SETFOCUS</td><td>通知编辑控件的父窗(通过WM_COMMAND获知):编辑框获得输入焦点</td></tr>
	<tr><td>_EN_KILLFOCUS</td><td>通知编辑控件的父窗(通过WM_COMMAND获知):编辑框失去输入焦点</td></tr>
	<tr><td>_EN_CHANGE</td><td>用户的操作可能会改变编辑控件的文本(与EN_UPDATE通知消息不同,该通知是在更新显示之后发送的)</td></tr>
	<tr><td>_EN_UPDATE</td><td>编辑控件显示变动的文本时的通知消息</td></tr>
	<tr><td>_EN_ERRSPACE</td><td>编辑控件不能为特定请求分配足够的空间的通知消息</td></tr>
	<tr><td>_EN_MAXTEXT</td><td>通知父窗,编辑控件当前输入文本已超过指定字符数(并作截尾处理)</td></tr>
	<tr><td>_EN_HSCROLL</td><td>用户单击了编辑控件的水平滚动条,父窗在屏幕更新之前被通知</td></tr>
	<tr><td>_EN_VSCROLL</td><td>用户单击了编辑控件的垂直滚动条,父窗在屏幕更新之前被通知</td></tr>
</table>

##示例
* **文本框内容改变事件**

		winform.edit.oncommand = function(id,event){
		        if(event == 0x300/*_EN_CHANGE*/){
		                io.print("被修改");
		        }
		}