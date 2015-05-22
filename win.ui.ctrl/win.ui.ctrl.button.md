#button-按钮控件



###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
	<tr><td>flat</td><td>1/0，浮动样式</td></tr>
	<tr><td>valign</td><td>垂直对齐：顶对齐(top)、居中(center)，底对齐(bottom)。可用样式改变</td></tr>	
</table>

###成员
<table>
	<tr><td>setIcon(__/*图标句柄*/)</td><td>设置图标,成功返回true,自动销毁原来的位图</td></tr>
	<tr><td>setImage(__/*图片句柄*/)</td><td>设置图片,成功返回true,自动销毁原来的位图</td></tr>
	<tr><td>setIcon(__/*图标句柄*/,false)</td><td>设置图标,成功返回控件原来的位图句柄,必须调用::DeleteObject()函数销毁该句柄</td></tr>
	<tr><td>setImage(__/*图片句柄*/,false)</td><td>设置图片,成功返回控件原来的位图句柄,必须调用::DeleteObject()函数销毁该句柄</td></tr>
</table>

###样式


<TABLE CELLSPACING=0 CELLPADDING=2>
<tr ><td>BS\_AUTOCHECKBOX<td>与复选框相同，但是当用户选择复选框时，检查标记出现在复选框中，而当用户再一次选择复选框时，检查标记就消失。
<tr ><td>BS\_AUTORADIOBUTTON<td>与单项按钮相同，但是当用户选择它的时候，这个按钮自动加亮显示自己并去掉同组中相同风格的其它单项按钮的选择状态。
<tr ><td>BS\_AUTO3STATE<td>与三态复选框相同，但是当用户选择该框时它会改变自己的状态。
<tr ><td>BS\_CHECKBOX<td>创建一个小方块，在它的右边显示文本（除非这个风格与BS\_LEFTTEXT风格一起使用）。
<tr ><td>BS\_DEFPUSHBUTTON<td>创建一个具有深黑边界的按钮。用户可以按下ENTER键以选择这个按钮。这个风格使用户可以快速地选择最相似的选项（缺省选项）。
<tr ><td>BS\_GROUPBOX<td>创建一个矩形区域，其中的按钮是成组的。与这种风格相关的任何文本将显示在矩形的左上角。
<tr ><td>BS\_LEFTTEXT<td>当与单项按钮风格或复选框风格一起使用时，文本出现在单项按钮或复选框的左边。
<tr ><td>BS\_OWNERDRAW<td>创建一个自画按钮。当按钮的视觉状态发生改变时，框架调用DrawItem成员函数。当使用CBitmapButton类的时候，必须设置这个风格。
<tr ><td>BS\_PUSHBUTTON<td>创建一个按钮，当用户选择该按钮时向所有者窗口发送一个WM_COMMAND消息。
<tr ><td>BS\_RADIOBUTTON<td>创建一个小圆形区域，在它的右边显示文本（除非这个风格与BS\_LEFTTEXT风格一起使用）。单项按钮通常成组使用但是只能独占选择。
<tr ><td>BS\_3STATE<td>与复选框类似，但是这个框不仅可以被选中，还可以被变灰。变灰状态通常用来标识该复选框已经被禁止。
</TABLE>


#####注意
* 按钮的Default和Cancel  
	>	tab顺序就是Z序，前键点控件，在弹出菜单中就可以排序.  
	>	id为1的按钮就是Default键，id为2的键就是Cancel 键。也就是你拖到窗体上的第一个按钮、第二个按钮。  
	>	或者右键点按钮，在弹出菜单中点选“最后面”，就成为默认按钮。连续选中两个按钮做上面的操作，则分别设为cancel键，一个default键  


##示例
* **按钮只能点击一次**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
		button={ bottom=200;right=344;left=176;top=112;z=1;text="button";cls="button" }
		)
		/*}}*/		
		winform.button.oncommand = function(id,event){
			//执行所需代码,然后设置按钮不可用
			winform.button.disabled=1;	
		}
		winform.show() 
		win.loopMessage();
