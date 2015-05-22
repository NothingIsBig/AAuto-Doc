# listview-列表视图控件

###设计属性
<table>
	<tr><td>变量名</td><td>名称，指定控件名称必须使用合法的变量名</td></tr>
	<tr><td>mode</td><td>模式</td></tr>
	<tr><td>gridLines</td><td>1/0，是否在行列间显示网格线</td></tr>
	<tr><td>fullRow</td><td>1/0，是否启用整行选择</td></tr>
	<tr><td>msel</td><td>1/0，允许多选。用_LBS_MULTIPLESEL样式改变</td></tr>
	<tr><td>asel</td><td>1/0，失去焦点时选中项目是否保持显示选定状态</td></tr>
</table>

###成员
<table>
	<tr><td>listview.getNotifyMessage()</td><td>!NMLISTVIEW.</td></tr>
	<tr><td>NMLISTVIEW.hdr</td><td>!nmhdl.</td></tr>
	<tr><td>NMLISTVIEW.ptAction</td><td>!point.</td></tr>
	<tr><td>NMLISTVIEW.iItem</td><td>鼠标指向项的行号,没有使用则为0</td></tr>
	<tr><td>NMLISTVIEW.iSubItem</td><td> 鼠标指向项的列序号,没有使用则为0</td></tr>
	<tr><td>NMLISTVIEW.uNewState</td><td>改变后状态,由_LVIS_作为前缀的常量指定</td></tr>
	<tr><td>NMLISTVIEW.uOldState</td><td>改变前状态,由_LVIS_作为前缀的常量指定</td></tr>
	<tr><td>NMLISTVIEW.uChanged</td><td>类似LVITEM结构体中的mask成员,以LVIF_前缀的常量标明改变的属性</td></tr>
	<tr><td>NMLISTVIEW.lParam</td><td>附加参数</td></tr>
	<tr><td>listview.getNotifyMessage(code,ptr)</td><td>该函数限用于onnotify通知回调函数中,code参数为通知码，如果ptr指向NMLISTVIEW对象则返回该对象.</td></tr>
	<tr><td>listview.getNotifyDispInfo()</td><td>!LV_DISPINFO.</td></tr>
	<tr><td>LV_DISPINFO.hdr</td><td>!nmhdl.</td></tr>
	<tr><td>LV_DISPINFO.item</td><td>!lvitem.</td></tr>
	<tr><td>listview.getNotifyDispInfo(code,ptr)</td><td>该函数限用于onnotify通知回调函数中,code参数为通知码，ptr参数为NMHDR指针,如果NMHDR指针指向LV_DISPINFO对象则返回该对象,否则返回空值</td></tr>
	<tr><td>lvitem.mask</td><td>掩码</td></tr>
	<tr><td>lvitem.iItem</td><td>行</td></tr>	
	<tr><td>lvitem.iSubItem</td><td>列</td></tr>
	<tr><td>lvitem.state</td><td>状态码 </td></tr>
	<tr><td>lvitem.stateMask</td><td>状态掩码</td></tr>
	<tr><td>lvitem.text</td><td>文本</td></tr>
	<tr><td>lvitem.cchTextMax</td><td>文本长度</td></tr>
	<tr><td>lvitem.iImage</td><td>图像索引</td></tr>
	<tr><td>lvitem.lParam</td><td>附加值</td></tr>
	<tr><td>lvitem.iIndent</td><td>缩进</td></tr>
	<tr><td>lvitem.iGroupId</td><td>组ID</td></tr>
	<tr><td>lvitem.cColumns</td><td>列数目</td></tr>
	<tr><td>lvitem.puColumns</td><td>!point. </td></tr>
	<tr><td>treeview.getItem(__)</td><td>返回LVITEM对象,参数为TVITEM结构体或指定部分成员的table对象.,可选使用参数一指定行号,参考二指定列序号,不指定项目序号,则取当前焦点节点作为序号</td></tr>
	<tr><td>treeview.setItem(__)</td><td>更新项节点,参数为LVITEM结构体或指定部分成员的table对象,如果参数未指定节点序号，则取当前焦点节点序号,成功返回true;,此函数可自动检测非空成员并自动设定相应mask位</td></tr>
	<tr><td>treeview.getItem()</td><td>!lvitem.</td></tr>
	<tr><td>lvcolumn.mask</td><td>掩码;</td></tr>
	<tr><td>lvcolumn.fmt</td><td>样式</td></tr>
	<tr><td>lvcolumn.cx</td><td>宽度</td></tr>
	<tr><td>lvcolumn.text</td><td>文本 </td></tr>
	<tr><td>lvcolumn.cchTextMax</td><td>文本缓冲区长度</td></tr>
	<tr><td>lvcolumn.iSubItem</td><td>列号 </td></tr>
	<tr><td>lvcolumn.iImage</td><td>图像索引</td></tr>
	<tr><td>lvcolumn.iOrder</td><td>序号</td></tr>
	<tr><td>listview.getColumn()</td><td>!lvcolumn.</td></tr>
	<tr><td>listview.getColumn(.(列参数表,列序号)</td><td>参数一可以为空,或是指定LVCOLUMN结构体成员键值的参数表,返回LVCOLUMN结构体</td></tr>
	<tr><td>listview.setColumn(.({cx=100},列序号)</td><td>改变列宽</td></tr>
	<tr><td>listview.setColumn(.(列参数表,列序号)</td><td>参数一指定LVCOLUMN结构体成员键值的参数表,也可以是LVCOLUMN结构体对象,自动设置掩码参数.</td></tr>
	<tr><td>listview.getEditControl()</td><td>开始编辑时返回编辑控件,此控件在完成编辑后会自动销毁,不必手动销毁,取消发送_WM_CANCELMODE消息即可,!edit.</td></tr>
	<tr><td>?.getEditControl</td><td>!edit.</td></tr>
	<tr><td>listview.editLable(.(行序号)</td><td>编辑指定项,无参数则编辑选定项,此函数成功返回编辑文本框句柄,返则返回0</td></tr>
	<tr><td>listview.setItemPos(__/*项索引*/,x,y)</td><td>设置图标项坐标</td></tr>
	<tr><td>listview.count</td><td>项目总数</td></tr>
	<tr><td>listview.insertColumn(.(列名,列宽,位置,样式)</td><td>第一个参数可以是标题字符串,图像索引,或者指定LVCOLUMN结构体成员的table对象,,其他参数都是可选参数,样式使用_LVCFMT_前缀的常量指定,例如_LVCFMT_LEFT为文本左对齐,如果列宽为-1,则自动调用fillParent(ind)函数填充剩余空间</td></tr>
	<tr><td>listview.setColumnText(.(位置,文本)</td><td>设置指定列文本</td></tr>
	<tr><td>listview.getColumnText(__)</td><td>取指定列文本</td></tr>
	<tr><td>listview.delColumn(__)</td><td>删除指定列</td></tr>
	<tr><td>listview.columnCount</td><td>列总数</td></tr>
	<tr><td>listview.clear()</td><td>清空所有项</td></tr>
	<tr><td>listview.getNextItem(.(起始索引,选项)</td><td>参数二为一个或多个 _LVNI_ 前缀的常量合并,默认为 _LVNI_ALL ,起始索引默认为0 </td></tr>
	<tr><td>listview.getFocused()</td><td>获取当前焦点项位置,返回数值,不存在焦点项则返回0</td></tr>
	<tr><td>listview.getSelection(.(起始索引) </td><td>获取选中项,返回数值,不存在选中项则返回0,可选指定起始索引,默认为0		</td></tr>
	<tr><td>listview.addItem(.(文本,位置,图像索引)</td><td>位置参数可省略,默认为count值,图像索引可省略,默认为-1,文本可以是一个指定多列文本的table数组,返回新增项行号</td></tr>
	<tr><td>listview.addItem(.(LVITEM对象,位置)</td><td>参数一可以是指定一个或多个LVITEM对象成员的table对象,text成员指定项目文件,也可以是一个指定多列文本的数组,位置参数可省略,默认为count值</td></tr>
	<tr><td>listview.setItemText(.(文本,行,列)</td><td>设置项目指定列文本,参数一也可是指定多列文本的数组(table对象),其他参数可选</td></tr>
	<tr><td>listview.getItemText(.(行,列,缓冲区长度)</td><td>列默认值为1,缓冲区最大字符数默认为100</td></tr>
	<tr><td>listview.getItemRect(.(行,列,RECT,选项)</td><td>返回表示项目表示项目区块的RECT结构体,除第一个参数以外,其他参数为可选参数,如果不指定列则返回所在行区块,使用_LVIR_前缀常量指定选项</td></tr>
	<tr><td>listview.getItemRect()</td><td>!rect.</td></tr>
	<tr><td>listview.hitTest(.(x坐标,y坐标,是否屏幕坐标)</td><td>该函数返回指定坐标的行号,列号,参数三可省略,默认为false.,如果不指定任何参数，则自动调用 win.getMessagePos() 获取消息坐标,第三个返回值指定测试结果,该值可以是一个或多个_LVHT_开头的常量组合,</td></tr>
	<tr><td>listview.setSelected(__/*项索引*/)</td><td>选中项</td></tr>
	<tr><td>listview.setSelected(__/*项索引*/,false)</td><td>取消选中项</td></tr>
	<tr><td>listview.getSelected(__/*项索引*/)</td><td>指定项是否选中状态</td></tr>
	<tr><td>listview.getChecked(__)</td><td>返回指定索引项是否选中</td></tr>
	<tr><td>listview.setChecked(__)</td><td>选定指定索引项</td></tr>
	<tr><td>listview.setItemState(.(项索引,状态位,掩码)</td><td>设置状态,参数三如果省略则使用参数二的值.</td></tr>
	<tr><td>listview.getItemState(.(项索引,状掩码 )</td><td>读取状态值</td></tr>
	<tr><td>listview.selIndex</td><td>当前选定项索引</td></tr>
	<tr><td>listview.fullRow</td><td>是否选中整行</td></tr>
	<tr><td>listview.delItem(__)</td><td>参数为数值，移除指定索引的项目</td></tr>
	<tr><td>listview.items</td><td>列表项集合(第一列),table对象 </td></tr>
	<tr><td>listview.setExtended(_LVS_EX__)</td><td>启用树视图指定扩展样式</td></tr>
	<tr><td>listview.setExtended(_LVS_EX__,false)</td><td>取消树视图指定扩展样式</td></tr>
	<tr><td>listview.getExtended()</td><td>获取树视图扩展样式</td></tr>
	<tr><td>listview.getExtended(_LVS_EX__)</td><td>获取树视图指定扩展样式</td></tr>
	<tr><td>listview.gridLines</td><td>是否显示网格线</td></tr>
	<tr><td>listview.setFocus()</td><td>设置焦点 </td></tr>
	<tr><td>listview.getTileViewInfo()</td><td>返回排列显示相关属性</td></tr>
	<tr><td>listview.setTileViewInfo()</td><td>设置排列显示相关属性</td></tr>
	<tr><td>listview.ensureVisible()</td><td>保证显示选中项,滚动到选中项</td></tr>
	<tr><td>listview.ensureVisible(__)</td><td>保证显示指定项,滚动到指定项</td></tr>
	<tr><td>listview.getImageList( _LVSIL__ )</td><td>获取指定图像列表,可选使用 _LVSIL_ 前缀常量指定类型</td></tr>
	<tr><td>listview.setImageList( imageList,_LVSIL__ )</td><td>获取指定图像列表,可选使用 _LVSIL_ 前缀常量指定类型</td></tr>
	<tr><td>listview.fillParent(.(列序号)</td><td>使指定列自适应父窗口宽度,如果不指定列默认调整最后一列</td></tr>
	<tr><td>listview.adjust</td><td>@.adjust = function(cx,cy){     winform.listview.fillParent(/*列序号*/); }</td></tr>
	<tr><td>listview.findItem(.(查找文本,起始位置,是否部份匹配,是否返回查询)</td><td>使用文本查找匹配项,除第一个参数外,所有参数可选,默认支持部份匹配,并查找所有项</td></tr>
	<tr><td>listview.addCtrl</td><td>@.addCtrl(,	edit ={ cls="edit";left=0;top=0;right=50;bottom=50;autoResize=false ;hide=1;edge=1;  },)</td></tr>
	<tr><td>win.ui.ctrl.listview()</td><td>列表视图,!listview.</td></tr>
	<tr><td>tileviewinfo.dwMask</td><td>@.dwMask = _LVTVIM__ ;</td></tr>
	<tr><td>tileviewinfo.dwFlags</td><td>@.dwFlags = _LVTVIF__ ;</td></tr>
	<tr><td>tileviewinfo.sizeTile</td><td>!size.</td></tr>
	<tr><td>tileviewinfo.cLines</td><td>行数</td></tr>
	<tr><td>tileviewinfo.rcLabelMargin</td><td>!rect.</td></tr>
</table>
####用法
* 更改指定列的宽度  

		winform.listview.setColumn( { cx = 50 },2 )
* 更改指定列宽度自适

		winform.listview.adjust = function(cx,cy){
    		winform.listview.fillParent(/*列序号*/);
		}
* 删除数据

		winform.listview.delItem(i);//i为索引
* 删除多条数据  
	删除数据要从最后开始删除

		for(i=#winform.listview.count;1;i--){
			winform.listview.delItem(i)
		}

## 示例

* **设置选择行**

* **删除所选行**
* **多线程下操作ListView**

		import win.ui;
		import win.ui.menu;
		import inet
		/*DSG{{*/
		var winform = ..win.form( bottom=360;parent=...;text="代理设置";right=436 )
		winform.add( 
		button9={ bottom=257;right=352;left=296;top=226;font=LOGFONT( name='宋体' );z=4;text="button9";cls="button" };
		static={ bottom=345;right=242;left=22;text="代理ip输入格式为：
		123.123.123.123:80";top=283;font=LOGFONT( name='宋体' );transparent=1;z=2;cls="static" };
		listview={ bgcolor=16777215;bottom=192;right=414;left=5;top=22;font=LOGFONT( name='宋体' );z=3;gridLines=1;fullRow=1;edge=1;cls="listview" };
		edit={ bottom=256;right=264;left=19;top=229;font=LOGFONT( name='宋体' );z=1;edge=1;cls="edit" }
		)
		/*}}*/
		winform.listview.onnotify = function(id,code,ptr){
		//当项目发生改变时
		    if( code == 0xFFFFFF9B/*_LVN_ITEMCHANGED*/ ){
		        if(winform.listview.selIndex){
		            winform.edit.text = winform.listview.getItemText(winform.listview.selIndex,1)   
		        }
		    }
		}
		fun=function(ip,hwnd){ 
		    import inet 
		    import inet.http
		    import win
		    import win.ui.ctrl.listview;
		    listview = win.ui.ctrl.listview();
		    listview.hwnd = hwnd;
		    inet.clearCookie()
		    http=inet.http("Mozilla/4.0",ip)
		    listview.setItemText("验证中",1,2);
		    html=http.get("http://www.ip138.com/ip2city.asp")
		    if(html){
		        listview.setItemText("可用",1,2);
		    }
		    else {
		        listview.setItemText("不可用",1,2);
		    }
		}
		winform.button9.oncommand = function(id,event){
		    //win.msgbox( winform.button9.text );
		    ip = "http://" ++ winform.edit.text
		    thread.create(fun,ip,winform.listview.hwnd)
		}
		winform.listview.addItem("201.76.212.250:8080",2)
		winform.listview.insertColumn("编号",200,1);
		winform.listview.insertColumn("编号",200,2);
		winform.show() 
		win.loopMessage();
		return winform;

*  **读取listview一行所有列有数据**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( bottom=383;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		 listview={ bgcolor=16777215;bottom=232;right=544;left=56;cls="listview";top=24;z=1;edge=1;fullRow=1 };
		 edit={ bottom=336;right=544;left=56;multiline=1;top=272;z=2;edge=1;cls="edit" }
		 )
		/*}}*/		
		 winform.listview.adjust = function(cx,cy){
		     winform.listview.fillParent(/*列序号*/);
		 } 		
		 winform.listview.insertColumn("列标题1",100,0x0/*_LVCFMT_LEFT*/) 
		 winform.listview.insertColumn("列标题2",100,0x0/*_LVCFMT_LEFT*/)		
		 winform.listview.addItem( { 
		     text={"第一行内容 ";"true"} 
		 } )
		 winform.listview.addItem( { 
		     text={"第二行内容 ";"false"} 
		 },2)		
		 winform.listview.onnotify = function(id,code,ptr){
	         select(code) {
	             case  0xFFFFFF9B/*_LVN_ITEMCHANGED*/ {
	                 var h = winform.listview.selIndex
	                 if(h){
	                     winform.edit.text = "";
	                     for(i=1;winform.listview.count;1){
	                         winform.edit.text + =  winform.listview.getItemText(h,i)
	                     }		                     
	                 }
	             }
	         }
		 }		
		 winform.show() 
		 win.loopMessage();

* 设置listview项的字体颜色

		import win.ui;
		import util;
		/*DSG{{*/
		var winform = ..win.form( bottom=399;parent=...;right=599;text="AAuto Form" )
		 winform.add( 
		 listview={ bgcolor=16777215;bottom=336;right=575;left=23;top=63;z=1;gridLines=1;edge=1;cls="listview" }
		 )
		/*}}*/
		 winform.listview.onnotify = function(id,code,ptr){
		     //var nmdr = win.ui.NMHDR(); raw.convert( ptr,nmdr );;
		}
		listviewColorize = (function () {
		     var NMLVCUSTOMDRAW = class {
		         struct nmcd = {
		             struct hdr = ..win.ui.NMHDR();
		             INT dwDrawStage;
		             pointer hdc;
		             struct rc = ::RECT();
		             int dwItemSpec;
		             INT uItemState;
		             int lItemlParam;
		         };
		         INT clrText;
		         INT clrTextBk;
		         int iSubItem;
		         INT dwItemType;
		         INT clrFace;
		         int iIconEffect;
		         int iIconPhase;
		         int iPartId;
		         int iStateId;
		         struct rcText = ::RECT();
		         INT uAlign;
		     }    
		     return function (listview) {
		         listview._colors = ..table.array(listview.count, 0);		         
		         listview.onnotify = function (id,code,ptr) {
		             if (code === 0xFFFFFFF4/*_NM_CUSTOMDRAW*/) {
		                 var nmlvcd = NMLVCUSTOMDRAW();
		                 raw.convert(ptr, nmlvcd);		                 
		                 select (nmlvcd.nmcd.dwDrawStage) {
		                     case 0x1/*_CDDS_PREPAINT*/
		                         return 0x20/*_CDRF_NOTIFYITEMDRAW*/
		                     case 0x10001/*_CDDS_ITEMPREPAINT*/ {
		                         raw.mixin(ptr, nmlvcd, { clrText = owner._colors[nmlvcd.nmcd.dwItemSpec + 1] });
		                         return 0/*_CDRF_DODEFAULT*/;
		                     }
		                 }
		             }
		         }        
		         listview.setItemColor = function (item, col) {
		             owner._colors[item] = col;
		         }         
		     }
		})();
		listviewColorize(winform.listview);
		winform.listview.insertColumn("字母", 150,0x0/*_LVCFMT_LEFT*/);
		var tab = {"a";"b";"c";"d";"e";"f"};
		for(i=1;#tab;1){    
		     item=winform.listview.addItem({tab[ i ]});
		      winform.listview.setItemColor(item, 0x0000FF);
		 }
		 winform.show() 
		 win.loopMessage();

* **用多个listview显示table中的不同数据**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( text="AAuto Form";bottom=439;parent=...;right=599 )
		 winform.add( 
		 boysRadio={ dl=1;checked=1;bottom=420;right=136;left=64;top=404;z=3;db=1;text="男生";cls="radiobutton" };
		 rangeStatic={ dl=1;bottom=420;text="范围：";left=8;top=400;center=1;z=2;db=1;right=60;transparent=1;cls="static" };
		 girlsRadio={ dl=1;bottom=420;text="女生";left=144;top=404;z=4;db=1;right=216;cls="radiobutton" };
		 listViewContainer={ dr=1;dl=1;bottom=392;right=592;left=8;dt=1;top=8;z=1;db=1;cls="picturebox" }
		 )
		/*}}*/
		
		import util.metaProperty;		
		var scores = {
		     boys = {
		         ["小明"] = 100;
		         ["小白"] = 95;
		         ["小杨"] = 98;
		     };
		     girls = {
		         ["小红"] = 91;
		         ["小李"] = 99;
		     };
		 };		
		class controlGroup {
		     ctor (parent) {
		         this[["parent_"]] = parent;
		         this[["selItem_"]] = null;
		     }		     
		     add = function (name, options) {
		         var ctrl = this[["parent_"]].addCtrl( [name] = options )[name];
		         ctrl.hide = true;
		         return ctrl;
		     }		     
		     delete = function (name) {
		         this[["parent_"]][name].close();
		     }		     
		     @_meta;
		 }
		 controlGroup._meta = ..util.metaProperty(
		     selItem = {
		         _set = function (v) {
		             if (owner[["selItem_"]]) owner[["parent_"]][owner[["selItem_"]]].hide = true;
		             owner[["parent_"]][v].hide = false;
		             owner[["selItem_"]] = v;
		         }
		         _get = function () {
		             return owner[["selItem_"]];
		         }
		     }
		 );		
		var listviewGroup = controlGroup(winform.listViewContainer);
		for (k, v in scores) {
		     var listview = listviewGroup.add(k, { bottom=384;right=584;left=0;top=0;z=2;edge=1;dl=1;dt=1;dr=1;db=1;cls="listview" });
		     listview.insertColumn("姓名", 100);
		     listview.insertColumn("成绩", 100);		     
		     for (name, score in v)
		         listview.addItem({ name; tostring(score) });
		 }
		 listviewGroup.selItem = "boys";		
		 winform.boysRadio.oncommand = function(id,event){
		     listviewGroup.selItem = "boys";
		 }		
		 winform.girlsRadio.oncommand = function(id,event){
		     listviewGroup.selItem = "girls";
		 }		
		 winform.show();
		 win.loopMessage();

* **listview控件添加combobox下拉框**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( right=522;bottom=300;parent=...;text="listview添加combobox " )
		winform.add( 
		listview={ bgcolor=16777215;bottom=217;right=505;left=26;fullRow=1;top=23;z=1;gridLines=1;edge=1;cls="listview" };
		static={ bottom=278;color=255;right=498;left=28;top=228;font=LOGFONT( h=-14;weight=700 );transparent=1;text="点击单元格查看效果。";z=2;cls="static" }
		)
		/*}}*/
		winform.listview.insertColumn("测试项1",80) 
		winform.listview.insertColumn("测试项2",100) 
		winform.listview.insertColumn("测试项3",100) 
		for(i=1;29;1){
		    winform.listview.addItem({tostring(i);"点我1";"点我2"});
		}
		winform.listview.onnotify = function(id,code,ptr){
		    if(code==0xFFFFFF4B){
		        if(!winform.listview.comboboxlable) return ; 
		        combobox = winform.listview.comboboxlable;
		        rc=winform.listview.getItemRect(combobox.listViewNotifyMessage.iItem,combobox.listViewNotifyMessage.iSubItem,2/*_LVIR_LABEL*/);
		        if(rc.top<rc.bottom-rc.top){
		            rc.top-=math.abs(rc.bottom);rc.bottom=rc.top;
		        }else {
		            rc.right += 5; rc.bottom += 5;
		        }
		        combobox.setRect(rc);
		        winform.listview.redraw();
		    }
		    if(code=0xFFFFFFFE/*_NM_CLICK*/ ){
		        var notifyMessage = winform.listview.getNotifyMessage(code,ptr);
		        if( ! notifyMessage.iItem && notifyMessage.iSubItem ) return ; 
		        var combobox = winform.listview.comboboxlable
		        if( ! combobox ){
		            winform.listview.addCtrl(
		            comboboxlable = {bottom=50;text="请选择";left=0;top=0;right=0;z=3;font = LOGFONT( h = 11 );mode="dropdown";edge=1;cls="combobox" ;
		items={ "1";"2";"3";"4";"5" };//添加下拉内容
		                    wndproc = function( hwnd, message, wParam, lParam ){
		                        if( ( message = 0x8/*_WM_KILLFOCUS*/) 
		                            || message == 0x101/*_WM_KEYUP*/ && wParam == 0xD/*_VK_RETURN*/){
		                            owner.parent.setItemText( owner.text, owner.listViewNotifyMessage.iItem
		                                , owner.listViewNotifyMessage.iSubItem );
		                            owner.show(true);
		                        ｝
		                    }  
		                }
		            )  
		            combobox = winform.listview.comboboxlable;
		        }
		        combobox.listViewNotifyMessage = notifyMessage; 
		        combobox.seltext=winform.listview.getItemText(notifyMessage.iItem,notifyMessage.iSubItem);
		        var rc=winform.listview.getItemRect( notifyMessage.iItem,notifyMessage.iSubItem,2/*_LVIR_LABEL*/ )
		        rc.right += 5; rc.bottom += 5;
		        combobox.setRect(rc);
		        combobox.show();
		        combobox.setFocus();
		    } 
		}
		winform.show()  
		win.loopMessage();


* **点击行切换选择，全选，取消全选**

		import win.ui;
		/*DSG{{*/
		var winform = ..win.form( text="AAuto Form";bottom=266;parent=...;right=349 )
		winform.add( 
		button={ bottom=244;text="全部勾选";left=133;top=213;z=3;right=208;cls="button" };
		static={ bottom=29;right=303;left=68;top=11;z=2;transparent=1;text="请使用鼠标左键、鼠标右键点击列表项";cls="static" };
		listview={ dr=1;dl=1;bgcolor=16777215;right=303;asel=false;cls="listview";fullRow=1;bottom=207;top=36;font=LOGFONT( name='SimSun' );msel=false;z=1;gridLines=1;edge=1;left=37 }
		)
		/*}}*/
		winform.button.oncommand = function(id,event){
			if winform.button.text="全部勾选" {
			    winform.button.text="全部取消"
			    for (i=1;winform.listview.count;1) {
			        winform.listview.setChecked(i)
			    }
			}else{
			    winform.button.text="全部勾选"
			    for (i=1;winform.listview.count;1) {
			        winform.listview.setChecked(i,false)
			    }
			}
		}
		winform.listview.onnotify = function(id,code,ptr){  
		    select(code) { 
		        case 0xFFFFFFFE/*_NM_CLICK*/{
		            var nm = winform.listview.getNotifyMessage(code,ptr)  
		            if( ! nm.iItem  ) return ;  
		            winform.listview.setChecked(nm.iItem,!winform.listview.getChecked(nm.iItem) ) 
		        }
		    }
		}
		//自适应列宽度 
		winform.listview.adjust = function(cx,cy){
		    winform.listview.fillParent(/*列序号*/);
		} 
		winform.listview.insertColumn("姓  名",80,,0x2/*_LVCFMT_CENTER*/) 
		winform.listview.insertColumn("电话号码",300,,0x2/*_LVCFMT_CENTER*/) 
		winform.listview.setExtended(0x4/*_LVS_EX_CHECKBOXES*/);
		winform.listview.addItem( { 
			text={"王永工";"13176768888"} 
		} )
		winform.listview.addItem("")
		winform.listview.addItem( {
			text={"冯有祥";"第三行内容"} 
		} )
		winform.listview.setItemText( {
			"刘光明";"第二行内容"
		},2);
		winform.show() 
		win.loopMessage();


*  **获取点击单元格的内容**

		import win.ui;
		import win.ui.menu;
		/*DSG{{*/
		var winform = ..win.form( bottom=249;parent=...;text="AAuto Form";right=349 )
		winform.add( 
		listview={ dr=1;dl=1;bgcolor=16777215;right=332;asel=false;cls="listview";fullRow=1;bottom=234;top=10;font=LOGFONT( name='SimSun' );msel=false;z=1;gridLines=1;edge=1;left=13 }
		)
		/*}}*/
		import mouse;
		winform.listview.onnotify = function(id,code,ptr){ 
		    select(code) {
		        case 0xFFFFFFFE/*_NM_CLICK*/    {
		            var nm = winform.listview.getNotifyMessage(code,ptr)
		            var pop = win.ui.popmenu(winform);
		            var text = winform.listview.getItemText(nm.iItem,nm.iSubItem)
		            if(#text){
		                pop.add(text,function(){
		                    winform.msgbox( text ,"提示")
		                })
		            }
		            var x,y = mouse.getPos()
		            pop.popup(x,y,true);
		        }   
		    }
		}
		//自适应列宽度 
		winform.listview.adjust = function(cx,cy){
		    winform.listview.fillParent(/*列序号*/);
		} 
		winform.listview.insertColumn("列标题1",100,,0x0/*_LVCFMT_LEFT*/) 
		winform.listview.insertColumn("列标题1",100,,0x0/*_LVCFMT_LEFT*/) 
		winform.listview.addItem({"第一行内容";"第二列"})
		winform.listview.addItem({"第二行内容";"第二列"})
		winform.listview.addItem({"第三行内容";"第二列"}) 
		winform.show() 
		win.loopMessage();
