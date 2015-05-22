#combobox-下拉组合框控件


###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>text</td><td>string，文本，指定窗口显示的文本</td></tr>
	<tr><td>items</td><td>table，选项集合，以分号分隔</td></tr>
	<tr><td>text</td><td>string，显示文本</td></tr>
	<tr><td>mode</td><td>控件模式，dropdown或dropdownlist或simple</td></tr>
<table>

### 成员
<table>
	<tr><td>add("文本")</td><td>添加到组合框,不支持排序</td></tr>
	<tr><td>insert("文本",插入位置)</td><td>默认添加到开始处,-1表示添加到尾部,支持0x100/*_CBS_SORT*/排序</td></tr>
	<tr><td>selIndex</td><td>获取或指定当前选中的项，当selIndex=0时选择为空项</td></tr>
	<tr><td>selText</td><td>读取或设置组合框当前选中文本</td></tr>
	<tr><td>find(__/*请输入文本*/)</td><td>查找列表项</td></tr>
	<tr><td>findEx</td><td>精确查找指定的项,找不到返回0 </td></tr>
	<tr><td>items</td><td>组合框内容</td></tr>
	<tr><td>limit</td><td>只写属性,修改最大允许输入的文本长度,如果设为0,则设定为默认长度0x7FFFFFFE,必须在控件初始化属性中启用横向滚动条,该属性才能生效</td></tr>
	<tr><td>text</td><td>组合框当前输入文本</td></tr>
	<tr><td>count</td><td>列表项数目</td></tr>
	<tr><td>delete()</td><td>删除当前选中项</td></tr>
	<tr><td>clear()</td><td>清除组合框所有内容</td></tr>
</table>

### 样式
<table>
	<tr><td>CBS\_AUTOHSCROLL<td>当用户在行尾输入一个字符时，自动把编辑控件中的文本向右滚动。如果没有设置该风格，则输入的文本信息只能多到填满矩形边框。
	<tr><td>CBS\_DROPDOWN<td>与CBS\_SIMPLE类似，但是除非用户选择了编辑控件旁边的图标，否则不会显示列表框。
	<tr><td>CBS\_DROPDOWNLIST<td>与CBS\_DROPDOWN类似，但是编辑控件被静态文本项代替，其中显示了列表框中的当前选择。
	<tr><td>CBS\_HASSTRINGS<td>包含了字符串组成的项的自画组合框。组合框维护着字符串的内存和指针，因此应用程序可以使用GetText成员函数从某个项获得文本。
	<tr><td>CBS\_OEMCONVERT<td>在组合框的编辑控件内输入的文本将从ANSI字符集转换到OEM字符集，然后再回到ANSI。当应用程序调用Windows的AnsiToOem函数把组合框中的一个ANSI字符串转换到OEM字符时，这能确保进行了合适的字符转换。这个风格对那些包含了文件名的组合框最有用，仅适用于用CBS\_SIMPLE或CBS\_DROPDOWN风格创建的组合框。
	<tr><td>CBS\_OWNERDRAWFIXED<td>列表框的拥有者负责画出其内容，列表框中所有项的高度是一样的。
	<tr><td>CBS\_OWNERDRAWVARIABLE<td>列表框的拥有者负责画出其内容，列表框中各项的高度是不一致的。
	<tr><td>CBS\_SIMPLE<td>任何时候都显示列表框。列表框的当前选择显示在编辑控件中。
	<tr><td>CBS\_SORT<td>自动排列输入到列表框的字符串。
	<tr><td>CBS\_DISABLENOSCROLL<td>当列表框没有足够的项以供滚动时，列表框将显示一个被禁止的垂直滚动条。如果没有这种风格，当列表框不包含足够的项时，这个滚动条将会被隐藏。
	<tr><td>CBS\_NOINTEGRALHEIGHT<td>指明组合框的大小就是应用程序在创建该组合框时指定的大小。通常，Windows会调整一些组合框的大小，使得组合框不需要显示部分项。
</TABLE>

###用法

* 添加项
* 插入项
* 选中项
* 获取选中项
* 查找项
* 删除项
* 清空项




##示例
* **输入长的文本**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
		button={ bottom=287;text="button";left=229;top=251;z=2;right=380;cls="button" };
		combobox={ bottom=136;right=409;left=170;top=116;style=0x40/*_CBS_AUTOHSCROLL*/;
		items={  };hscroll=1;z=1;text="可以输入很长很长的内容喽";mode="dropdown";edge=1;cls="combobox" }
		)
		/*}}*/

		::SendMessageInt(winform.combobox.hwnd,0x141/*_CB_LIMITTEXT*/,0xFFFF,0)

		winform.show() 
		win.loopMessage();

* **省市连联动**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=249;parent=...;right=349;text="AAuto Form" )
		winform.add( 
		cmbProvince={ bottom=100;text="combobox";left=144;top=80;right=264;z=1;
		items={  };mode="dropdownlist";edge=1;cls="combobox" };
		static={ bottom=99;align="right";right=142;left=96;top=80;z=3;text="省:";transparent=1;cls="static" };
		cmbCity={ bottom=140;text="combobox2";left=144;top=120;right=264;z=2;
		items={  };mode="dropdownlist";edge=1;cls="combobox" };
		static2={ bottom=136;align="right";right=142;left=96;top=120;z=4;text="市:";transparent=1;cls="static" }
		)
		/*}}*/		
		var tCity = {};
		tCity["北京市"] = { '东城区'; '西城区';'崇文区';'宣武区';'朝阳区';'丰台区';'石景山区'; '海淀区';'门头沟区'; '房山区';
		    '通州区';'顺义区';'昌平区';'大兴 区';'怀柔区';'平谷区';'密云县';'延庆县'};
		tCity["天津市"] = { '和平区';'河东区'; '河西区'; '南开区'; '河北区'; '红桥区'; '塘沽区'; '汉沽区'; '大港区'; '东丽区'; 
		    '西青区'; '津南区'; '北辰区'; '武清区'; '宝坻区'; '宁河县'; '静海县'; '蓟县'}; 
		tCity["上海市"] = { '黄浦区';'卢湾区'; '徐汇区';'长宁区';'静安区';'普陀区';'闸北区';'虹口区'; '杨浦区'; '闵行区'; 
		    '宝山区'; '嘉定区'; '浦东新区'; '金山区'; '松江区'; '青浦区'; '南汇区'; '奉贤区'; '崇明县'}; 
		tCity["重庆市"] = { '万州区';'涪陵区';'渝中区';'大渡口区';'江北区';'沙坪坝区';'九龙坡区';'南岸区';'北碚区';
		    '万盛区';'双桥区';'渝北区';'巴南区';'黔江区';'长寿区';'江津区';'合川区';'永川区';'南川区';'綦江县';'潼南县';
		    '铜梁县';'大足县';'荣昌县';'璧山县';'梁平县';'城口县';'丰都县';'垫江县';'武隆县';'忠县';'开县';'云阳县';
		    '奉节县';'巫山县';'巫溪县';'石柱土家族自治县';'秀山土家族苗族自治县';'酉阳土家族苗族自治县';'彭水苗族土家族自治县'};		
		winform.cmbProvince.oncommand = function(id,event){
		    if( event == 0x1/*_CBN_SELCHANGE*/ ){
		        winform.cmbCity.clear()
		        winform.cmbCity.items = tCity[winform.cmbProvince.selText]
		        winform.cmbCity.selIndex = 1;
		    } 
		}		
		winform.cmbProvince.items = {"北京市"; "天津市";"上海市";"重庆市";}
		winform.cmbProvince.selIndex = 1;
		winform.cmbProvince.oncommand(,1)		
		winform.show() 
		win.loopMessage();

* **combobox示例(待完善功能:删除,选择...)**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( right=400;bottom=297;max=false;text="下拉框控件基本操作演示";parent=...)
		 winform.add( 
		 editAll={ bottom=279;right=206;left=14;multiline=1;top=115;z=4;edge=1;cls="edit" };
		 btnAdd={ bottom=69;right=329;left=177;top=40;z=3;text="添加到下拉框";cls="button" };
		 editAdd={ bottom=64;text="edit";left=14;top=41;z=2;right=166;edge=1;cls="edit" };
		 btnEdit={ bottom=272;right=383;left=229;top=235;z=5;text="修改下拉框";cls="button" };
		 static={ bottom=117;right=154;left=16;top=96;z=6;transparent=1;text="下拉框数据( 每行一个 ):";cls="static" };
		 combobox={ bottom=30;right=90;left=15;
		 items={  };text="combobox";z=1;top=10;mode="dropdown";edge=1;cls="combobox" }
		 )
		/*}}*/		
		 winform.btnAdd.oncommand = function(id,event){		
		     //添加到下拉框
		    winform.combobox.insert( winform.editAdd.text,1  ) 		     
		     //修改下拉框当前选中项
		    winform.combobox.selIndex = 1;		     
		     winform.editAll.text = string.join( winform.combobox.items,'\r\n' ) 		     
		 }		
		 winform.btnEdit.oncommand = function(id,event){		
		     //文本按行拆分为数组
		    var items = string.split( winform.editAll.text ,'<\r\n>' );		     
		     //修改下拉框数据
		    winform.combobox.items = items;		     
		     //修改下拉框当前选中项
		    winform.combobox.selIndex = 1;
		 }		
		 winform.show() 
		 win.loopMessage();


* **设置combobox模式为simple的大小**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		winform.add( 
		combobox={ bottom=258;right=376;left=273;
		items={ "aa";"bb";"cc" };text="combobox";z=1;top=238;mode="simple";edge=1;cls="combobox" }
		)
		/*}}*/

		//调整combobox控件大小
		winform.combobox.setPos(,,100,20)

		winform.show() 
		win.loopMessage();

* **选择后更改combobox的text内容**


		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		combobox={ 
		items={ "a";"b";"c";"d" };bottom=182;right=351;left=70;top=156;z=1;mode="dropdown";edge=1;cls="combobox" }
		)
		/*}}*/

		winform.combobox.oncommand = function(id,event){

		    if( event = 0x1/*_CBN_SELCHANGE*/ ) { 
		        winform.setTimeout( function(){
		            winform.combobox.text = winform.combobox.text+"被选中";
		        }) 
		    }  
		}
		  
		winform.show() 
		win.loopMessage();
