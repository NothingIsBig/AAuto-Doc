


#控件公共成员

###属性
<table>
<tr><td>cls：string</td><td>设计时类名</td></tr>
<tr><td>className：string</td><td>运行时类名</td></tr>
<tr><td>text：string</td><td>可读写，文本属性<br/>支持：static、button、edit、richedit、checkbox、radiobutton、groupbox、combobox</td></r>
<tr><td>hwnd</td><td>控件句柄</td></tr>
<tr><td>id：number</td><td>控件ID</td></tr>
<tr><td>_parentForm</td><td>控件所在的父窗口(指win.form对象)</td></tr>
<tr><td>hide：boolean</td><td>控件是否隐藏</td></tr>
<tr><td>disabled</td><td>是否禁用</td></tr>
<tr><td>left</td><td>左侧坐标</td></tr>
<tr><td>right</td><td>右侧坐标</td></tr>
<tr><td>top</td><td>顶部坐标</td></tr>
<tr><td>bottom</td><td>底部坐标</td></tr>
<tr><td>width</td><td>宽度</td></tr>
<tr><td>height</td><td>高度</td></tr>
<tr><td>theme</td><td>外观主题,例如,winform.button.theme = "Explorer",winform.button.theme = false</td></tr>
<tr><td>capture</td><td>是否捕获全局鼠标消息</td></tr>
</table>
###方法
<table>
<tr><td>getParent()</td><td>返回父窗口</td></tr>
<tr><td>setParent(/*窗口对象*/)</td><td>改变父窗口</td></tr>
<tr><td>setFocus()</td><td>设置焦点</td></tr>
<tr><td>show()</td><td>显示控件</td></tr>
<tr><td>getRect()</td><td>获取控件区块位置(::RECT结构体)</td></tr>
<tr><td>setRect(rc)</td><td>设置控件屏幕区块位置(::RECT结构体) </td></tr>
<tr><td>getClientRect()</td><td>获取控件客户区块位置(::RECT结构体),rect.</td></tr>
<tr><td>clientRect</td><td>获取控件客户区块位置(::RECT结构体)</td></tr>
<tr><td>setPos(x坐标,y坐标,宽,高,插入位置,参数)</td><td>调整窗口位置或排序,所有参数可选,同时指定x,y坐标则移动位置,同时指定宽高则改变大小,指定插入位置(句柄或_HWND前缀常量)则调整Z序</td></tr>
<tr><td>getPos()</td><td>返回相对坐标,宽,高,x,y,cx,cy=win.getPos(hwnd)</td></tr>
<tr><td>getFont()</td><td>获得控件字体(::LOGFONT结构体)</td></tr>
<tr><td>setFont()</td><td>指定LOGFONT字体对象,或逻辑字体句柄</td></tr>
<tr><td>modifyStyle(remove,add)</td><td></td></tr>
<tr><td>modifyStyleEx(remove,add)</td><td></td></tr>
<tr><td>redraw()</td><td>刷新</td></tr>
<tr><td>close()</td><td>关闭控件</td></tr>
</table>



<table>
<theader>
<tr><th>名称</th><th>说明</th></tr>
</theader>
<tbody>
<tr><td>redraw</td><td></td><tr>
<tr><td>redrawTransparent</td><td>sssss</td><tr>
<tr><td>invalidate</td><td></td></tr>
<tr><td>update</td><td></td></tr>
<tr><td>capture</td><td></td></tr>
<tr><td>text</td><td></td></tr>
<tr><td>hide</td><td></td></tr>
<tr><td>close</td><td></td></tr>
<tr><td>autoResize</td><td></td></tr>
<tr><td>modifyStyle</td><td></td></tr>
<tr><td>modifyStyleEx</td><td></td></tr>
<tr><td>show</td><td></td></tr>
<tr><td>disabled</td><td></td></tr>
<tr><td>tailWndproc</td><td></td></tr>
<tr><td>wndproc</td><td></td></tr>
<tr><td>adjust</td><td></td></tr>
<tr><td>left</td><td></td></tr>
<tr><td>right</td><td></td></tr>
<tr><td>top</td><td></td></tr>
<tr><td>bottom</td><td></td></tr>
<tr><td>height</td><td></td></tr>
<tr><td>width</td><td></td></tr>
<tr><td>getPos</td><td></td></tr>
<tr><td>setPos</td><td></td></tr>
<tr><td>getRect</td><td></td></tr>
<tr><td>setRect</td><td></td></tr>
<tr><td>getClientRect</td><td></td></tr>
<tr><td>_savePosRatio</td><td></td></tr>
<tr><td>getParent</td><td></td></tr>
<tr><td>setParent</td><td></td></tr>
<tr><td>addCtrl</td><td></td></tr>
<tr><td>setFocus</td><td></td></tr>
<tr><td>vScroll</td><td></td></tr>
<tr><td>hScroll</td><td></td></tr>
<tr><td>getFont</td><td></td></tr>
<tr><td>setFont</td><td></td></tr>
<tr><td>theme</td><td></td></tr>
<tr><td>rect</td><td></td></tr>
<tr><td>clientRect</td><td></td></tr>
<tr><td>font</td><td></td></tr>
<tr><td>messageOnly</td><td></td></tr>
<tr><td>createEmbed</td><td></td></tr>
</tbody>
</table>
