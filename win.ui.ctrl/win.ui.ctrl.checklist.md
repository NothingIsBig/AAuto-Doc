#checklist-复选框列表控件
  复选框列表，继承自listview，不要用有关列的操作

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>文本，指定窗口显示的文本</td></tr>
<tr><td>items</td><td>table，选项集合，以分号分隔</td></tr>
<tr><td>msel</td><td>1/0，允许多选。用_LBS_MULTIPLESEL样式改变</td></tr>
</table>

###成员
<table>
	<tr><td>addItem(文本,位置)</td><td>位置参数可省略,默认为count值,返回新增项行号</td></tr>
	<tr><td>editLable(行序号)</td><td>编辑指定项,无参数则编辑选定项,此函数成功返回编辑文本框句柄,返则返回0</td></tr>
	<tr><td>getFocused()</td><td>获取当前焦点项位置,返回数值,不存在焦点项则返回0</td></tr>
	<tr><td>getSelection(起始索引) </td><td>获取选中项,返回数值,不存在选中项则返回0,可选指定起始索引,默认为0</td></tr>
	<tr><td>setSelected(__/*项索引*/)</td><td>选中项</td></tr>
	<tr><td>setSelected(__/*项索引*/,false)</td><td>取消选中项</td></tr>
	<tr><td>getSelected(__/*项索引*/)</td><td>指定项是否选中状态</td></tr>
	<tr><td>getChecked(__)</td><td>返回指定索引项是否选中</td></tr>
	<tr><td>setChecked(__)</td><td>选定指定索引项</td></tr>
	<tr><td>selIndex</td><td>当前选定项索引</td></tr>
	<tr><td>findItem(查找文本,起始位置,是否部份匹配,是否返回查询)</td><td>使用文本查找匹配项,除第一个参数外,所有参数可选,默认支持部份匹配,并查找所有项</td></tr>
	<tr><td>delItem(__)</td><td>参数为数值，移除指定索引的项目</td></tr>
	<tr><td>clear()</td><td>清空所有项</td></tr>
	<tr><td>items</td><td>列表项集合(第一列),table对象 </td></tr>
	<tr><td>count</td><td>项目总数</td></tr>
</table>

###用法

* 添加项

		winform.checklist.addItem("内容");
		winform.checklist.addItem("内容",1);//倒序
		
* 插入项
		
		winform.checklist.addItem("内容",index);//插入到指定位置
* 勾选中项
		
		winform.checklist.setChecked(__) //选定指定索引项
* 判断是否勾选

		winform.checklist.getChecked(__) //返回指定索引项是否选中
* 获取勾选中项


* 选择项

		winform.checklist.setSelected(__/*项索引*/) //选中项
		winform.checklist.setSelected(__/*项索引*/,false) //取消选中项
		winform.checklist.getSelected(__/*项索引*/) //指定项是否选中状态
* 查找项
* 删除项
* 清空项

* 找出所有选中的项

		for(i=1;count;1){
			if(winform.checklist.getChecked(i)){
				console.log("第"++i++"项:"++winform.checklist.getItemText(i,1))
			}
		}
