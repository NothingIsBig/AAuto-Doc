#scintilla

<table>
<tr><td>scintilla.create(父窗口,左,顶,宽,高)</td><td>创建一个 Scintilla 代码编辑框</td></tr>
<tr><td>sci.setSavePoint()</td><td>设置保存点，将文档设置为未修改状态，通常在新建文档或保存动作之后执行</td></tr>
<tr><td>sci.getLine(行号)</td><td>取指定行文本，行号从 0 开始</td></tr>
<tr><td>sci.getTextRange(开始位置,结束位置)</td><td>取指定区域内的文本</td></tr>
<tr><td>sci.addText(文本)</td><td>向当前光标处追加文本</td></tr>
<tr><td>sci.appendText(文本)</td><td>向文档尾部追加文本</td></tr>
<tr><td>sci.insertText(文本, 位置)</td><td>向文档指定位置追加文本</td></tr>
<tr><td>sci.clearAll()</td><td>清空文档内容</td></tr>
<tr><td>sci.clearDocumentStyle()</td><td>清空文档所有样式</td></tr>
<tr><td>sci.getCharAt(位置)</td><td>取得文档指定位置的字符的代码</td></tr>
<tr><td>sci.getStyleAt(位置)</td><td>取得文档指定位置的样式</td></tr>
<tr><td>sci.findText(文本)</td><td>在整个文档中搜索指定文本，找到返回开始位置和结束位置，找不到则返回 -1</td></tr>
<tr><td>sci.findText(文本,标识)</td><td>同上，但可以指定标识参数为 _SCFIND_ 开头的常量以设置搜索的模式</td></tr>
<tr><td>sci.findText(文本,标识,开始位置,结束位置)</td><td>同上，但可以指定搜索的范围,当不是正则搜索模式的时候，开始位置可以大于结束位置，意为反向查找</td></tr>
<tr><td>sci.searchAnchor()</td><td>设置当前位置为搜索的起始位置</td></tr>
<tr><td>sci.searchNext(文本)</td><td>从 searchAnchor 调用时的位置开始往后搜索指定文本</td></tr>
<tr><td>sci.searchNext(文本,标识)</td><td>同上，但可以指定标识参数为 _SCFIND_ 开头的常量以设置搜索的模式</td></tr>
<tr><td>sci.searchPrev(文本)</td><td>从 searchAnchor 调用时的位置开始往前搜索指定文本</td></tr>
<tr><td>sci.searchPrev(文本,标识)</td><td>同上，但可以指定标识参数为 _SCFIND_ 开头的常量以设置搜索的模式</td></tr>
<tr><td>sci.targetFromSelection()</td><td>设置搜索的目标为选中区域（仅在选中区域内搜索）</td></tr>
<tr><td>sci.searchInTarget(文本)</td><td>在指定目标内搜索文本</td></tr>
<tr><td>sci.replaceTarget(文本)</td><td>将指定目标替换为指定文本</td></tr>
<tr><td>sci.replaceTargetRe(.文本)</td><td>同 replaceTarget，但支持正则表达式</td></tr>
<tr><td>sci.getTag()</td><td></td></tr>
<tr><td>sci.cut()</td><td>剪切</td></tr>
<tr><td>sci.copy()</td><td>复制</td></tr>
<tr><td>sci.paste()</td><td>粘贴</td></tr>
<tr><td>sci.clear()</td><td>清除</td></tr>
<tr><td>sci.copyAllowLine()</td><td>同 copy，但当没有选中任何区域时，复制光标所在行</td></tr>
<tr><td>sci.copyRange(开始位置,结束位置)</td><td>复制指定区域的文本到剪贴板</td></tr>
<tr><td>sci.copyText(文本)</td><td>将指定文本放到剪贴板内</td></tr>
<tr><td>sci.undo()</td><td>撤销</td></tr>
<tr><td>sci.redo()</td><td>重做</td></tr>
<tr><td>sci.emptyUndoBuffer()</td><td>清空撤销缓存（之前的所有撤销数据将被清除）</td></tr>
<tr><td>sci.beginUndoAction()</td><td></td></tr>
<tr><td>sci.endUndoAction()</td><td></td></tr>
<tr><td>sci.addUndoAction(标识字符串,标识)</td><td></td></tr>
<tr><td>sci.setSel(开始位置,结束位置)</td><td>选中指定区域</td></tr>
<tr><td>sci.goToPos(位置)</td><td>将光标移至指定区域</td></tr>
<tr><td>sci.goToLine(行号)</td><td>将光标移至指定行</td></tr>
<tr><td>sci.setEmptySelection(位置)</td><td>将光标移至指定位置，并且清除其余选区</td></tr>
<tr><td>sci.selectAll()</td><td>全选</td></tr>
<tr><td>sci.lineFromPosition(位置)</td><td>取指定位置的文本所在的行号</td></tr>
<tr><td>sci.positionFromLine(行号)</td><td>取指定行号的首字符位置</td></tr>
<tr><td>sci.lineLength(行号)</td><td>取指定行的文本长度</td></tr>
<tr><td>sci.startStyling()</td><td></td></tr>
<tr><td>sci.setStyling()</td><td></td></tr>
<tr><td>sci.setLineState(行号,状态)</td><td></td></tr>
<tr><td>sci.getLineState(行号)</td><td></td></tr>
<tr><td>sci.styleResetDefault()</td><td>重置默认风格</td></tr>
<tr><td>sci.styleClearAll()</td><td>将所有风格样式设置为与 _STYLE_DEFAULT 相同</td></tr>
<tr><td>sci.styleSetFont(风格号,字体)</td><td>设置指定风格号字体</td></tr>
<tr><td>sci.styleGetFont(风格号)</td><td>取指定风格号字体</td></tr>
<tr><td>sci.styleSetSize(风格号,字号)</td><td>设置指定风格号字号</td></tr>
<tr><td>sci.styleGetSize(风格号)</td><td>取指定风格号字号</td></tr>
<tr><td>sci.styleSetBold(风格号,是否加粗)</td><td>设置指定风格号是否为粗体</td></tr>
<tr><td>sci.styleGetBold(风格号)</td><td>取指定风格号是否为粗体</td></tr>
<tr><td>sci.styleSetItalic(风格号,是否倾斜)</td><td>设置指定风格号是否为斜体</td></tr>
<tr><td>sci.styleGetItalic(风格号)</td><td>取指定风格号是否为斜体</td></tr>
<tr><td>sci.styleSetUnderline(风格号,是否有下划线)</td><td>设置指定风格号是否为粗体</td></tr>
<tr><td>sci.styleGetUnderline(风格号)</td><td>取指定风格号是否有下划线</td></tr>
<tr><td>sci.styleSetFore(风格号,颜色)</td><td>设置指定风格号的前景色</td></tr>
<tr><td>sci.styleGetFore(风格号)</td><td>取指定风格号的前景色</td></tr>
<tr><td>sci.styleSetBack(风格号,颜色)</td><td>设置指定风格号的背景色</td></tr>
<tr><td>sci.styleGetBack(风格号)</td><td>取指定风格号的背景色</td></tr>
<tr><td>sci.setStyle(风格号,字体,字号,粗体,斜体,下划线,前景色,背景色)</td><td>设置风格的简易方法，任意参数可空，留空为不设置指定项</td></tr>
<tr><td>sci.setMarginType(边栏号,类型)</td><td>设置指定边栏类型，边栏号可以为 0～4，类型为 _SC_MARGIN_SYMBOL(符号) 或 _SC_MARGIN_NUMBER(数字)</td></tr>
<tr><td>sci.getMarginType(边栏号)</td><td>取指定边栏类型</td></tr>
<tr><td>sci.setMarginWidth(边栏号,宽度)</td><td>设置指定边栏宽度</td></tr>
<tr><td>sci.getMarginWidth(边栏号)</td><td>取指定边栏宽度</td></tr>
<tr><td>sci.setMarginMask(边栏号,标识)</td><td></td></tr>
<tr><td>sci.getMarginMask(边栏号)</td><td></td></tr>
<tr><td>sci.setMarginSensitive(边栏号,是否响应鼠标点击)</td><td>设置指定边栏是否响应鼠标点击，如果响应，当鼠标点击时，会发送一个 _SCN_MARGINCLICK 通知</td></tr>
<tr><td>sci.getMarginSensitive(边栏号)</td><td>取指定边栏是否响应鼠标点击</td></tr>
<tr><td>sci.setMarginCursor(边栏号,鼠标指针)</td><td>设置指定边栏的鼠标指针，鼠标指针参数为以 _SC_CURSOR 开头的常量</td></tr>
<tr><td>sci.getMarginCursor(边栏号)</td><td>取指定边栏的鼠标指针</td></tr>
<tr><td>sci.setKeywords(索引,关键字列表)</td><td>设置关键字列表，索引可以为 0～８，关键字列表中的各关键字可以用空格、制表符或换行符分割</td></tr>
<tr><td>sci.sendEditor(消息号,附加参数一,附加参数二)</td><td>向编辑器发送指定消息，可以实现编辑器提供的所有功能，消息号为以 _SCI_ 开头的常量</td></tr>
<tr><td>sci.length</td><td>文档字符串长度（字数）</td></tr>
<tr><td>sci.text</td><td>文档内容</td></tr>
<tr><td>sci.selText</td><td>被选中的文本，设置该属性可以替换当前选区的文本</td></tr>
<tr><td>sci.readonly</td><td>是否只读</td></tr>
<tr><td>sci.styleBits</td><td>风格位</td></tr>
<tr><td>sci.targetStart</td><td>搜索开始位置，供 searchInTarget 使用</td></tr>
<tr><td>sci.targetEnd</td><td>搜索结束位置，供 searchInTarget 使用</td></tr>
<tr><td>sci.searchFlags</td><td>搜索模式，以 _SCFIND_ 开头的常量，供 searchInTarget 使用</td></tr>
<tr><td>sci.canPaste</td><td>能否粘贴</td></tr>
<tr><td>sci.pasteConvertEndings</td><td>是否转换粘贴数据的换行模式为当前文档的换行模式</td></tr>
<tr><td>sci.status</td><td></td></tr>
<tr><td>sci.canUndo</td><td>能否撤销</td></tr>
<tr><td>sci.canRedo</td><td>能否重做</td></tr>
<tr><td>sci.undoCollection</td><td>是否自动收集撤销步骤</td></tr>
<tr><td>sci.lineCount</td><td>当前文档的行数</td></tr>
<tr><td>sci.firstVisibleLine</td><td>当前文档的首个可见行</td></tr>
<tr><td>sci.linesOnScreen</td><td>当前文档在屏幕上的可见行数</td></tr>
<tr><td>sci.modify</td><td>文档是否已被修改，配合 setSavePoint 使用</td></tr>
<tr><td>sci.currentPos</td><td>当前光标位置</td></tr>
<tr><td>sci.anchor</td><td>当前锚位置</td></tr>
<tr><td>sci.selectionStart</td><td>选区开始位置</td></tr>
<tr><td>sci.selectionEnd</td><td>选区结束位置</td></tr>
<tr><td>sci.curLine</td><td>当前行文本</td></tr>
<tr><td>sci.selectionIsRectangle</td><td></td></tr>
<tr><td>sci.selectionMode</td><td></td></tr>
<tr><td>sci.endStyled</td><td>最后被渲染的字符代码</td></tr>
<tr><td>sci.selAlpha</td><td>选区透明度</td></tr>
<tr><td>sci.selEOLFilled</td><td></td></tr>
<tr><td>sci.controlCharSymbol</td><td>控制符号的替换字符代码，0 为不启用</td></tr>
<tr><td>sci.marginLeft</td><td>边栏左侧外边距</td></tr>
<tr><td>sci.marginRight</td><td>边栏右侧外边距</td></tr>
<tr><td>sci.fontQuality</td><td>字体质量，为 _SC_EFF_ 开头的常量</td></tr>
<tr><td>sci.codepage</td><td>代码页，显示中文可以设置为 936 或以 _SC_CP_ 开头的常量</td></tr>
<tr><td>sci.tabWidth</td><td>制表符宽度</td></tr>
<tr><td>sci.useTabs</td><td>是否使用制表符，如果为 false，则使用空格代替制表符</td></tr>
<tr><td>sci.indent</td><td>缩进</td></tr>
<tr><td>sci.lexer</td><td>词法分析器，是以 _SCLEX_ 开头的常量</td></tr>
<tr><td>sci.lexerLanguage</td><td>词法分析器名称，区分大小写，如 cpp</td></tr>
<tr><td>sci.describeKeywordSets</td><td>关键字解释列表</td></tr>
<tr><td>sci.styleBitsNeeded</td><td>当前词法分析器需要的风格位</td></tr>
</table>