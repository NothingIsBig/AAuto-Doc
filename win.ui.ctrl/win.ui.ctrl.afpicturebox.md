#afpicturebox

<table>
<tr><td>text</td><td>文本属性</td></tr>
<tr><td>hwnd</td><td>控件句柄</td></tr>
<tr><td>id</td><td>控件ID</td></tr>
<tr><td>parent</td><td>父窗口</td></tr>
<tr><td>parent</td><td>winform.</td></tr>
<tr><td>hide</td><td>控件是否隐藏</td></tr>
<tr><td>disabled</td><td>控件ID</td></tr>
<tr><td>left</td><td>左侧坐标</td></tr>
<tr><td>right</td><td>右侧坐标</td></tr>
<tr><td>top</td><td>顶部坐标</td></tr>
<tr><td>bottom</td><td>底部坐标</td></tr>
<tr><td>redraw()</td><td>刷新</td></tr>
<tr><td>show(true__)</td><td>显示控件</td></tr>
<tr><td>rect</td><td>控件区块位置(::RECT结构体)</td></tr>
<tr><td>clientRect</td><td> 控件客户区块位置(::RECT结构体)</td></tr>
<tr><td>font</td><td>控件字体(::LOGFONT结构体)</td></tr>
<tr><td>clientRect</td><td> 获取控件客户区块位置(::RECT结构体)</td></tr>
<tr><td>theme</td><td>外观主题,例如,winform.button.theme = "Explorer",winform.button.theme = false</td></tr>
<tr><td>modifyStyle(remove,add)</td><td>如果指定第三个参数，则使用此参数调用::SetWidnowPos </td></tr>
<tr><td>modifyStyleEx(remove,add)</td><td>如果指定第三个参数，则使用此参数调用::SetWidnowPos</td></tr>
<tr><td>capture</td><td>是否捕获全局鼠标消自息</td></tr>
<tr><td>close()</td><td>关闭控件窗口</td></tr>
<tr><td>invalidate(__/*可选使用::RECT()对象指定客户区*/)</td><td>使窗口绘图区无效</td></tr>
<tr><td>invalidate(__/*可选使用::RECT()对象指定客户区*/,0)</td><td>使窗口绘图区无效,不刷新背景</td></tr>
<tr><td>update()</td><td>重绘invalidate函数指定的区块</td></tr>
<tr><td>setFocus()</td><td>设置焦点 </td></tr>
<tr><td>setPos(x坐标,y坐标,宽,高,插入位置,参数)</td><td>调整窗口位置或排序,所有参数可选,同时指定x,y坐标则移动位置,同时指定宽高则改变大小,指定插入位置(句柄或_HWND前缀常量)则调整Z序</td></tr>
<tr><td>getPos()</td><td>返回相对坐标,宽,高,x,y,cx,cy=win.getPos(hwnd)</td></tr>
<tr><td>image</td><td>图片</td></tr>
<tr><td>mode</td><td>显示模式，"normal"=左上角显示，"scale"=缩放显示，"center"=居中显示</td></tr>
<tr><td>frameCount</td><td>帧数（仅对GIF有效）</td></tr>
<tr><td>currentFrame</td><td>当前帧索引（仅对GIF有效）</td></tr>
<tr><td>frameDelays</td><td>帧延时（table）</td></tr>
</table>