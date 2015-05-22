#treeview-树形控件

###设计属性
<table>
	<tr><td>chkbox</td><td>1/0，是否启用复选框</td></tr>
	<tr><td>nLine</td><td>1/0，是否隐藏节点之间的连接线</td></tr>
	<tr><td>nLineRoot</td><td>1/0，是否隐藏连接到根节点的线条</td></tr>
	<tr><td>nButton</td><td>1/0，隐藏节点按钮</td></tr>
	<tr><td>nTip</td><td>1/0，是否隐藏Tooltip</td></tr>
	<tr><td>infoTip</td><td>1/0，是否启用Infotip</td></tr>
	<tr><td>editable</td><td>1/0，是否允许编辑节点文本</td></tr>
	<tr><td>singleExpand</td><td>1/0，仅允许展开当前选中节点，自动收缩其它节点</td></tr>
	<tr><td>fullRow</td><td>1/0，是否启用整行选择</td></tr>
	<tr><td>asel</td><td>1/0，失去焦点时选中项目是否保持显示选定状态</td></tr>
</table>

###成员
<table>
	<tr><td>insertItem(插入项参数,父项,前面的子项)</td><td>参数一可以是普通文本,也可以是TVITEM结构体或指定部分成员的table对象,<br/>
	参数一可使用数组添加多个兄弟节点,使用children成员添加多个子节点,<br/>
	参数二指定父项(可省略),<br/>
	参数三指定插入位置前面的子项(可省略),返回新节点句柄,<br/>
	示例, <br/>
	var item  winform.treeview.insertItem( text = "根目录" ),<br/>
	item = winform.treeview.insertItem("子节点",item),<br/>
	此函数可自动检测非空成员并自动设定相应mask位</td></tr>
	<tr><td>setSelected()</td><td>不选定任何节点</td></tr>
	<tr><td>setSelected(hItem)</td><td>选定节点,参数指定节点句柄</td></tr>
	
	<tr><td>getNotifyDispInfo(code,ptr)</td><td>该函数限用于onnotify通知回调函数中,code参数为通知码，ptr参数为NMHDR指针,如果NMHDR指针指向TV_DISPINFO对象则返回该对象,否则返回空值</td></tr>
	<tr><td>getNotifyMessage(code,ptr)</td><td>该函数限用于onnotify通知回调函数中,code参数为通知码，ptr参数为NMHDR指针,如果code不是大于_TVN_FIRST,并小于_TVN_LAST的消息,该函数返回空值,否则返回NMTREEVIEW对象.</td></tr>
	<tr><td>getEditControl()</td><td>开始编辑时返回编辑控件,此控件在完成编辑后会自动销毁,不必手动销毁,取消发送_WM_CANCELMODE消息即可,edit.</td></tr>
	<tr><td>visibleCount</td><td>获取可见项总数</td></tr>
	<tr><td>imageList</td><td> 获取设置图像列个,支持 win.imageList 对象</td></tr>
	<tr><td>hitTest(x坐标,y坐标,是否屏幕坐标)</td><td>该函数返回指定坐标的句柄,参数三可省略,默认为false.,如果不指定任何参数，则自动调用 win.getMessagePos() 获取消息坐标,第二个返回值指定测试结果,该值可以是一个或多个_TVHT_开头的常量组合,</td></tr>
	<tr><td>setDropHiLite(hItem)</td><td>选定节点,似拖放操作的目标项目高亮显示,参数指定节点句柄</td></tr>
	<tr><td>selFirstVisible(hItem)</td><td>选定节点并设置到可视区第一行,参数指定节点句柄</td></tr>
	<tr><td>getItemRect(hItem)</td><td>返回句柄指定节点整行区块(RECT对象),省略节点句柄则取当前选中节点</td></tr>
	<tr><td>getItemRect(hItem,true)</td><td>返回句柄指定节点文本区块(RECT对象),省略节点句柄则取当前选中节点</td></tr>
	<tr><td>getEditHwnd()</td><td>返回编辑文本框句柄; </td></tr>
	<tr><td>expand(hItem)</td><td>展开项,参数为节点句柄,省略则取当前选中项</td></tr>
	<tr><td>collapse(hItem)</td><td>折叠项,参数为节点句柄,省略则取当前选中项</td></tr>
	<tr><td>collapseReset(hItem)</td><td>折叠并删除子项,参数为节点句柄,省略则取当前选中项</td></tr>
	<tr><td>toggle(hItem)</td><td>折叠的就展开，展开的就折叠 ,参数为节点句柄,省略则取当前选中项</td></tr>
	<tr><td>expandPartial(hItem)</td><td>部分展开,参数为节点句柄,省略则取当前选中项</td></tr>
	<tr><td>count</td><td>获取项目总数</td></tr>
	<tr><td>ensureVisible(hItem)</td><td>确保指定项目是可见的，通过展开父项目或滚动树型控件窗,参数为节点句柄</td></tr>
	<tr><td>editLable(hItem)</td><td>开始编辑项,参数为节点句柄</td></tr>
	<tr><td>endEdit(true)</td><td>结束编辑并取消</td></tr>
	<tr><td>endEdit()</td><td>结束编辑并 </td></tr>
	<tr><td>getItem(__)</td><td>返回TVITEM对象,参数为TVITEM结构体或指定部分成员的table对象.,参数一也可以是空值,或树节点句柄,如果参数未指定节点句柄，则取当前选中节点</td></tr>
	<tr><td>setItem(__)</td><td>更新项节点,参数为TVITEM结构体或指定部分成员的table对象,如果参数未指定节点句柄，则取当前选中节点,成功返回true;,此函数可自动检测非空成员并自动设定相应mask位</td></tr>
	<tr><td>getItemText(节点句柄,缓冲区长度)</td><td>返回节点文本,省略节点参数则取当前选中节点,缓冲区长度参数可省略,默认为100</td></tr>
	<tr><td>setItemText(节点句柄,文本)</td><td>设置节点文本,省略节点参数则取当前选中节点</td></tr>
	<tr><td>clear()</td><td>清空所有项</td></tr>
	<tr><td>delItem(hItem__/*节点句柄*/)</td><td>删除节点,参数:节点句柄 </td></tr>
	<tr><td>getChildItem(hItem__/*节点句柄*/)</td><td>返回子节点,参数:节点句柄 </td></tr>
	<tr><td>getNextSibling (hItem__/*节点句柄*/)</td><td>返回后面的兄弟节点,参数:节点句柄 </td></tr>
	<tr><td>getPrevSibling(hItem__/*节点句柄*/)</td><td>返回前面的兄弟节点,参数:节点句柄</td></tr>
	<tr><td>getParentItem(hItem__/*节点句柄*/)</td><td>返回父节点,参数:节点句柄</td></tr>
	<tr><td>getNextItem(hItem__/*节点句柄*/)</td><td>返回下一个节点,第二个参数可选使用 _TVNI_ 前缀的常量指定选项</td></tr>
	<tr><td>getFirstVisible()</td><td>返回第一个可见节点,参数:节点句柄</td></tr>
	<tr><td>getNextVisible(hItem__/*节点句柄*/)</td><td>返回下一个可见节点,参数:节点句柄</td></tr>
	<tr><td>getPrevVisible(hItem__/*节点句柄*/)</td><td>返回上一个可见节点,参数:节点句柄</td></tr>
	<tr><td>getChecked(hItem__/*节点句柄*/)</td><td>返回指定项是否选中</td></tr>
	<tr><td>setChecked(hItem__/*节点句柄*/)</td><td>选定指定项</td></tr>
	<tr><td>getSelection()</td><td>返回当前选中节点 </td></tr>
	<tr><td>getDropHilight()</td><td>返回拖放操作的目标项目;</td></tr>
	<tr><td>getRoot()</td><td>返回根节点</td></tr>
	<tr><td>enum</td><td>@.enum(,	function(hItem,parent){,		io.print( ,			"节点",hItem ,			"父节点",parent ,		)					,		winform.treeview.setChecked(hItem),	},)</td></tr>
	<tr><td>getImageList( _TVSIL__ )</td><td>获取指定图像列表,可选使用 _LVSIL_ 前缀常量指定类型</td></tr>
	<tr><td>setImageList( imageList,_TVSIL__ )</td><td>获取指定图像列表,可选使用 _LVSIL_ 前缀常量指定类型</td></tr>
	<tr><td>getItem()</td><td>tvitem.</td></tr>
	<tr><td>tvitem.mask</td><td>可使用一个或多个TVIF_开头的常量组合,以指定当前结构体哪些成员有效</td></tr>
	<tr><td>tvitem.hItem</td><td>节点句柄</td></tr>
	<tr><td>tvitem.state</td><td>可使用一个或多上TVIS_开头的常量组合</td></tr>
	<tr><td>tvitem.stateMask</td><td>数值</td></tr>
	<tr><td>tvitem.text</td><td>文本 </td></tr>
	<tr><td>tvitem.cchTextMax</td><td>取文本时可在此指定缓冲区长度</td></tr>
	<tr><td>tvitem.iImage</td><td>项目非选取状态下，要使用的image在图象列表中的索引</td></tr>
	<tr><td>tvitem.iSelectedImage</td><td>项目选取状态下，要使用的image在图象列表中的索引</td></tr>
	<tr><td>tvitem.cChildren</td><td>子项目数目,如果为-1则向父窗体发送_TVN_GETDISPINFO通知消息</td></tr>
	<tr><td>tvitem.lParam</td><td>数值</td></tr>
</table>

###用法
* 添加根节点

		root = winform.treeview.insertItem("根节点")

* 获取当前选择的节点  

		var hItem = winform.treeview.getSelection();

* 获取父节点  

		hItem = winform.treeview.getNextItem(hItem,3/*_TVGN_PARENT*/)
* 设置节点文本

		setItemText(节点句柄,文本)	设置节点文本,省略节点参数则取当前选中节点

* 获取节点文本

		var text = winform.treeview.getItemText(hItem)
* 展开节点

		expand(hItem)	展开项,参数为节点句柄,省略则取当前选中项
* 折叠节点

		collapse(hItem)	折叠项,参数为节点句柄,省略则取当前选中项
* 折叠节点并删除子节点

		collapseReset(hItem)	折叠并删除子项,参数为节点句柄,省略则取当前选中项
* 切换展开状态

		toggle(hItem)	折叠的就展开，展开的就折叠 ,参数为节点句柄,省略则取当前选中项
* 删除节点

		delItem(hItem__/*节点句柄*/)
##示例
* **取得外部SysTreeView32的节点的坐标（代码段）**

		getItRect = function(row,TTprcs){
		    //声明外部EXE中的API函数
		    SendMessageByStruct_c = TTprcs.remoteApi("int(int,INT,int,struct &)","User32.dll","SendMessageA" ) 
		    hitem=TTview.getSelection()
		    rc=RECT();
		    rc.left=tonumber(hitem)
		    _rect=0;   
		    _rect =TTprcs.malloc (..raw.sizeof(rc),0x1000,0x40)
		    TTprcs.writeStruct(_rect,rc)  
		    SendMessageByStruct_c(htree,0x1104/* LVM_GETITEMRECT*/, row, rc); 
		    rc,rc1= TTprcs.readStruct(_rect,rc)
		    x = rc.left + (rc.right - rc.left) / 2; 
		    y = rc.top + (rc.bottom - rc.top) / 2;
		    x1,y1=win.toScreen(htree,x,y) 
		    TTprcs.mfree(_rect); //释放在外部进程的内存 
		    //  win.msgbox(x1+"   "+y1,"AAuto") 
		    return x1,y1; 
		}

* **treeview图标文件**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		treeview={ bgcolor=16777215;bottom=250;right=260;left=110;top=75;asel=false;z=1;edge=1;cls="treeview" }
		)
		/*}}*/
		import win.imageList;
		var imageList = win.imageList(16,15).add("\res\iml.gif",0xFF00FF/*透明色*/)
		winform.treeview.setImageList( imageList,0/*_TVSIL_NORMAL*/ )
		winform.treeview.insertItem(
		    text="内核库";
		    iImage=7;//数字是图标索引
		    iSelectedImage=1;
		    children={
		        {text="math";iSelectedImage=1;};
		        {text="com";iSelectedImage=1;};
		        {text="io";iSelectedImage=1;};
		        {text="raw";iSelectedImage=1;};
		        {text="string";iSelectedImage=1;};
		        {text="table";iSelectedImage=1;};
		        {text="time";iSelectedImage=1;};
		    }
		)
		winform.show() 
		win.loopMessage();

* **自定义treeview图标**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=239;parent=...;text="AAuto Form";right=311 )
		winform.add( 
		treeview={ bgcolor=16777215;bottom=232;right=304;left=8;fullRow=1;top=8;nButton=1;z=1;singleExpand=false;asel=false;exstyle=512;cls="treeview" }
		)
		/*}}*/
		import console;
		import win.imageList;
		var imageList = win.imageList(16, 16);
		imageList.add('GIF89a \0\x10\0\xA2\0\0`\x8F\xBF\xE2\xEE\xF1\x8E\xAE\xC8HWj\xBF\xCF\xD6\xFE\xFF\xFF\xFF\xFF\xFF\xFF\0\xFF!\xF9\x04\0\0\0\0\0,\0\0\0\0 \0\x10\0\0\x03\xB6x\x07\xDC.*\xCAI\x07\xB97\xE8R`\xC4D\x10\x05`4\x0C\x8C\xE04\x02\xB1\x18\x1C\x19f\x01\x07(\'!\xEC<\xDF\xBD\x85\x9A&T\xE3\x14n\x07\xD4\x0E\xA0j\xAA~\0\xD8n(4"O*"I\x05\x08@\xA2G&ic\xC51\x05\x81\xC6\xA5\xE9Z1\x89A\x1Bn\x80\x16\xA7\xD3\0(\x97\x0B/\'Qi\x04]\x83]_,\0:\x1AEGs-\x83\x82\x82\x85@\x0C!hFr\x7F\x88\x94-{mRDhU\x8C\x7F;\x91+P0\x8A^d\x98\')k\x0E^I01\xABq\x1C\x03sn\x0E:I:\x18\xAB\x18-\xB9\x99\xBB\0t_\'(\xC8\x02\xCB\xAE&\xCA\xD1\xCF\x14s\xC4\x13\t\0;');
		winform.treeview.setImageList(imageList, 0/*_LVSIL_NORMAL*/)
		winform.treeview.onnotify = function(id,code,ptr){
			var nmdr = win.ui.NMHDR(); raw.convert( ptr,nmdr );;
			if (nmdr.code = 0xFFFFFE6A/*_TVN_ITEMEXPANDEDA*/) {
				var nm = owner.getNotifyMessage(code, ptr);
				if (nm.action = 0x2/*_TVE_EXPAND*/) {
					owner.setItem(
						hItem = nm.itemNew.hItem;
						iImage = 1;
						iSelectedImage = 1;
					);
				}
				else {
					owner.setItem(
						hItem = nm.itemNew.hItem;
						iImage = 0;
						iSelectedImage = 0;
					);
				}
			}
		}
		var root = winform.treeview.insertItem(
			text = "根节点";
		);
		var item = winform.treeview.insertItem({
			text = "子节点一";
		}, root);
		winform.show();
		win.loopMessage();


* **加载sqlite里的分级数据到treeview**

		import win.ui;
		import win.ui.menu;
		import sqlite;
		import mouse;
		import win.inputBox;
		/*DSG{{*/
		var winform = ..win.form( bottom=400;parent=...;right=600;text="AAuto Form" )
		winform.add( 
		button2={ bottom=158;text="创建测试数据";left=484;top=116;z=3;right=587;cls="button" };
		button={ bottom=62;right=587;left=484;top=21;z=2;text="创建测试数据库";cls="button" };
		treeview={ bgcolor=16777215;bottom=380;right=471;left=24;top=18;asel=false;z=1;edge=1;cls="treeview" };
		static={ bottom=344;right=581;left=491;text="PS：右键菜单
		        更改节点";top=314;transparent=1;z=5;cls="static" };
		button3={ bottom=257;right=586;left=483;top=216;z=4;text="保存到数据库";cls="button" }
		)
		/*}}*/
		//保存时，先遍历生成code代码，再分拆成两部分写入数据库。
		winform.button3.oncommand = function(id,event){
			if (winform.treeview.count > 0){
				var sqlConnection = sqlite("/data.db")
				if(sqlConnection.existsTable("test") ){
					sqlConnection.exec("drop table test")
				}
				sqlConnection.exec( "create table test(
					code, 
					content 
					);"
				)
				var Fid = 1
				var ID = 1
				mark = ""
				winform.treeview.enum(
					function(hItem,parent){
						if(winform.treeview.getParentItem(hItem) = null){
							if(string.len(Fid) = 1){
								tmp = "0" + tostring(Fid)
							}
							else {
								tmp  = tostring(Fid)
							}	
							var New = tostring(tmp) + " | " + winform.treeview.getItemText(hItem)
							winform.treeview.setItemText(hItem,New)					
							Fid = Fid + 1
						}
						else {
							var TParent = winform.treeview.getItemText(parent)
							var CParent = string.left(TParent,string.find(TParent," | ")-1,true)
							if(mark == CParent){
								if(string.len(ID) = 1){
									tmp = "0" + tostring(ID)
								}
								else {
									tmp  = tostring(ID)
								}
								New = tostring(CParent) ++ tostring(tmp) ++ " | " ++ winform.treeview.getItemText(hItem)
								winform.treeview.setItemText(hItem,New)
								ID = ID + 1
							}
							else {
								New = CParent + "01" + " | " + winform.treeview.getItemText(hItem)
								winform.treeview.setItemText(hItem,New)
								ID = 2
								mark = CParent
							}
						}
					}
				)	
				winform.treeview.enum(
					function(hItem,parent){
						var tmp = winform.treeview.getItemText(hItem)
						var code = string.left(tmp,string.find(tmp," | ")-1,true)
						var tmp = string.right(tmp,string.len(tmp)-string.find(tmp," | ")-2,true)
						winform.treeview.setItemText(hItem,tostring(tmp))
						sqlConnection.exec( "insert into test values ('"++code++"', '"++tmp++"');")
					}
				)
				sqlConnection.close()
				winform.msgbox("保存成功！")
			}
			else {
				var sqlConnection = sqlite("/data.db")
				if(sqlConnection.existsTable("test") ){
					sqlConnection.exec("drop table test")
				}
				sqlConnection.close()
			}
		}
		//连接数据库，将数据读到tab表
		var sqlConnection = sqlite("/data.db")
		if(sqlConnection.existsTable("test")){
			tab = sqlConnection.getTable("select * from test")
		}
		sqlConnection.close()
		//添加测试数据
		winform.button2.oncommand = function(id,event){
			var hitem = winform.treeview.insertItem( text="程序目录" );
			var hSubItem = winform.treeview.insertItem( { text="子目录" },hitem/*父节点*/);	
			hitem = winform.treeview.insertItem( { 
					text = "children数组指定子节点"; 
					children = { 
						{ text = "子节点"  };
						{ text = "子节点2" };
						{ text = "子节点3";
					  	children = {
					  		"a";"b";"c";{ text = "d" } 
					  	}
						};
					}
			} ) 
		}
		//建立数据库
		winform.button.oncommand = function(id,event){
			var sqlConnection = sqlite("/data.db")
			if( not sqlConnection.existsTable("test") ){
				sqlConnection.exec( "create table test(
					code, 
					content 
					);"
				)
			}
			sqlConnection.close()	
		}
		//数据库读出的表不是空的执行加载，先加上code编码，完成后再去掉。
		if(table.count(tab) > 0){
			for(i=1;#tab){
				if(string.len(tab[i].code)=2){
					self[tab[i].code] = winform.treeview.insertItem(tab[i].code + " | " +tab[i].content)		
				}
				else {
					var Node_parent = self[string.left(tab[i].code,string.len(tab[i].code)-2)]
					self[tab[i].code] = winform.treeview.insertItem(tab[i].code +" | " + tab[i].content,Node_parent)
				}
			}	
			winform.treeview.enum(
				function(hItem,parent){
					var tmp = winform.treeview.getItemText(hItem)
					var tmp = string.right(tmp,string.len(tmp)-string.find(tmp," | ")-2,true)
					winform.treeview.setItemText(hItem,tostring(tmp))
				}
			)
		}
		//以下是右键菜单
		winform.treeview.onnotify = function(id,code,ptr){
			if(code = 0xFFFFFFFB/*_NM_RCLICK*/){
				var x,y = mouse.getPos()
				var hItem,tvht = winform.treeview.hitTest(x,y,true);
				var menu = win.ui.popmenu(winform)
				menu.add("添加第一级数据",
					function(){
						inputbox = win.inputBox(winform.hwnd)
		 				inputbox.text = "请输入添加的数据"
						inputbox.info.text = "请在下面输入添加的文字"
						inputtext = inputbox.doModal();
						if(inputtext){				
							winform.treeview.insertItem(inputtext)
						}
					}
				)
				menu.add("添加子数据",
					function(){
						inputbox = win.inputBox(winform.hwnd)
		 				inputbox.text = "请输入添加的子数据"
						inputbox.info.text = "请在下面输入添加的文字"
						inputtext = inputbox.doModal();
						if(inputtext){
							winform.treeview.insertItem(inputtext,winform.treeview.getSelection())	
						}
						winform.treeview.expand(winform.treeview.getSelection())
					｝
				)
				menu.add("删除",
					function(){
						winform.treeview.delItem(winform.treeview.getSelection())
					}
				)
				menu.popup(x,y,true);
			} 
		}
		winform.show() 
		win.loopMessage();
		return winform;




* **加载分组table到treeview**

		import win.ui;
		import mouse;
		import win.ui.menu;
		import win.inputBox;
		/*DSG{{*/
		var winform = ..win.form( bottom=400;parent=...;right=600;text="AAuto Form" )
		winform.add( 
		treeview={ bgcolor=16777215;bottom=391;right=264;left=8;top=8;asel=false;z=1;edge=1;cls="treeview" };
		static={ bottom=34;right=449;left=279;text="static";top=11;transparent=1;z=2;cls="static" };
		static2={ bottom=57;right=393;left=280;text="static2";top=35;z=3;transparent=1;cls="static" }
		)
		/*}}*/
		var tab = {
			{code="01";content="test1"}
			{code="0101";content="test1.1"}
			{code="0102";content="test1.2"}
			{code="010201";content="test1.2.1"}
			{code="010202";content="test1.2.2"}
			{code="010203";content="test1.2.3"}
			{code="0103";content="test1.3"}
			{code="02";content="test2"}
			{code="0201";content="test2.1"}
			{code="0202";content="test2.2"}
		}
		var tab_p = {}
		if(table.count(tab) > 0){
			for(i=1;#tab){
				if(string.len(tab[i].code)=2){
					self[tab[i].code] = winform.treeview.insertItem(tab[i].code + " | " +tab[i].content)		
					table.insert(tab_p,tostring(self[tab[i].code]),table.count(tab_p)+1)
				}
				else {
					var Node_parent = self[string.left(tab[i].code,string.len(tab[i].code)-2)]
					self[tab[i].code] = winform.treeview.insertItem(tab[i].code +" | " + tab[i].content,Node_parent)
					table.insert(tab_p,tostring(self[tab[i].code]),table.count(tab_p)+1)
				}
			}	
			winform.treeview.enum(
				function(hItem,parent){
					var tmp = winform.treeview.getItemText(hItem)
					var tmp = string.right(tmp,string.len(tmp)-string.find(tmp," | ")-2,true)
					winform.treeview.setItemText(hItem,tostring(tmp))
				}
			)
		}
		winform.treeview.onnotify = function(id,code,ptr){
			if( code == 0xFFFFFFFE/*_NM_CLICK*/ ){  
				var hItem = winform.treeview.hitTest()  
				if( hItem ){ 
					winform.static.text = tostring(hItem)
					for(i=1;#tab_p){
						if(tab_p[i] = tostring(hItem)){
							winform.static2.text = tostring(i)
						}
					}
				}
			}
		elseif(code = 0xFFFFFFFB/*_NM_RCLICK*/){
				var x,y = mouse.getPos()
				var hItem,tvht = winform.treeview.hitTest(x,y,true);
				var menu = win.ui.popmenu(winform)
				menu.add("添加第一级数据",
					function(){
						inputbox = win.inputBox(winform.hwnd)
		 				inputbox.text = "请输入添加的数据"
						inputbox.info.text = "请在下面输入添加的文字"
						inputtext = inputbox.doModal();
						if(inputtext){				
							InsItem = winform.treeview.insertItem(inputtext)
						}
						table.insert(tab_p,tostring(InsItem),table.count(tab_p)+1)
						table.insert(tab,inputtext,table.count(tab)+1)
					}
				)
				menu.add("添加子数据",
					function(){
						N = 0
						C = 0
						inputbox = win.inputBox(winform.hwnd)
		 				inputbox.text = "请输入添加的子数据"
						inputbox.info.text = "请在下面输入添加的文字"
						inputtext = inputbox.doModal();
						if(inputtext){
							InsItem = winform.treeview.insertItem(inputtext,winform.treeview.getSelection())
							//获得选择节点位置
							for(i=1;#tab_p){
								if(tab_p[i] = tostring(winform.treeview.getSelection())){
									N = i
									break ;
								}
							}
							//获得选择节点的总子节点个数	
							SItem = winform.treeview.getSelection()
							winform.treeview.enum(					
								function(hItem,parent){
									phItem = winform.treeview.getParentItem(hItem)
									while(phItem){
										if(tostring(phItem) = tostring(SItem)){
											C = C + 1
										}
										phItem = winform.treeview.getParentItem(phItem)
									}	
								}
							)
							N = N + C
							table.insert(tab,inputtext,N)
							table.insert(tab_p,tostring(InsItem),N)
						}
						winform.treeview.expand(winform.treeview.getSelection())
					｝
				)
				menu.add("删除",
					function(){
						N = 0
						C = 0
						for(i=1;#tab_p){
							if(tab_p[i] = tostring(winform.treeview.getSelection())){
								N = i
								break ;
							}
						}
						//获得选择节点的总子节点个数	
						SItem = winform.treeview.getSelection()
						winform.treeview.enum(					
							function(hItem,parent){
								phItem = winform.treeview.getParentItem(hItem)
								while(phItem){
									if(tostring(phItem) = tostring(SItem)){
										C = C + 1
									}
									phItem = winform.treeview.getParentItem(phItem)
								}	
							}
						)
						io.open()
						for (i=N+C;N;-1){				
							io.print(tostring(i))
							table.remove(tab,i)
							table.remove(tab_p,i)
						}
						winform.treeview.delItem(winform.treeview.getSelection())
					}
				)
				menu.popup(x,y,true);
			} 
		}
		winform.show() 
		win.loopMessage();
		return winform;
* **加载目录树到treeview**  
	第一种  （文件在前，目录在后）
	
		import win.ui;
		import fsys;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		treeview={ ah=1;bgcolor=16777215;vscroll=1;right=589;left=5;asel=false;top=4;bottom=388;z=1;hscroll=1;edge=1;cls="treeview" }
		)
		/*}}*/
		enum = function(p,f,l) begin
		    fsys.enum(  p, 
		                "*.*", 
		                function(dir,file,fullpath,findData){ 
		                        if(file){
		                            if(string.right(file,4)==string.right(f,4) or string.right(f,2)==".*"){ 
		                                winform.treeview.insertItem({text=file;},l);
		                            }
		                        }
		                    else{
		                            k = winform.treeview.insertItem({text=dir;},l);
		                            enum(fullpath,f,k);
		                    }
		                } ,false
		              );
		end;
		enum("/",".*",);
		winform.show() 
		win.loopMessage();

   第二种（目录和文件按名称排序）

	
		import win.ui;
		import fsys;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;text="AAuto Form";right=599 )
		winform.add( 
		treeview={ ah=1;bgcolor=16777215;vscroll=1;right=589;left=5;asel=false;top=4;bottom=388;z=1;hscroll=1;edge=1;cls="treeview" }
		)
		/*}}*/
		enum = function(p,f,l) begin
		    fsys.enum(  p, 
		                "*.*", 
		                function(dir,file,fullpath,findData){ 
		                        if(file){
		                            if(string.right(file,4)==string.right(f,4) or string.right(f,2)==".*"){ 
		                                winform.treeview.insertItem({text=file;},l);
		                            }
		                        }
		                    else{
		                            k = winform.treeview.insertItem({text=dir;},l);
		                            enum(fullpath,f,k);
		                    }
		                } ,false
		              );
		end;
		enum("/",".*",);
		winform.show() 
		win.loopMessage();