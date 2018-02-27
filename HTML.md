# 所有标签
* 所有标签对应的元素拥有以下属性（全局属性）的几个或全部：
* asscesskey————指定一个(组)键盘快捷键来访问该元素，可使用该属性的元素包括 A、AREA（逐渐被遗弃了，尽量别用）、BUTTON、INPUT、LABEL、LEGEND、TEXTAREA。
* class————为元素指定的CSS类。在JS的元素中，可通过className属性访问。
* contenteditable————设置的值为true或空字符串时，元素内容可被用户编辑。如果这个属性没有被设置，他的默认值会继承他父element的。
* data-*————被统称为自定义属性。是HTML文档与DOM对象之间的信息交换通道，通常用于脚步获取元素自定义数据。
* contextmenu————该属性指定自定义右击菜单dom的id。浏览器未实现该属性。
* dir————语言的方向。值为"ltr"（例如对英语有效）或"rtl"（例如对阿拉伯语有效）或"auto"（由代理决定）。该属性被强烈要求用在 BDO 标签上。
* draggable————指定元素是否能被拖动。该属性必须指定为"true"或"false"值。默认上，只有被选中的文本、图片或链接能被拖动。对于其他的element来说，为了让拖拽机制能够正常工作，ondragstart必须被设置的。
* dropzone————决定丢到一个元素上的内容类型。值的类型包括：copy(表示丢放时创建一个被拖拽元素的副本)、move(表示被拖拽元素会移动到该位置)、link(将会被拖拽的数据创建一个链接)。浏览器未实现该属性。
* hidden————这个布尔属性表示元素还没有或是不再存在。例如某个元素须在登录处理完成后才可以被使用，那么就应当隐藏该元素。这个属性不能使用在能够适时的显示而又被隐藏内容里（例如选项卡）。
* id————元素在文档中的唯一标识符。
* lang————元素内容的语言类型例如 en、zh、en-us。
* style————指定内联的样式声明。
* tabindex————值必须是一个整数。指定按下tab键时，元素(可获取焦点元素)能否获取焦点或获取焦点的顺序：负值表示元素能通过鼠标但不能通过tab键获取焦点、0表示可通过鼠标和tab键到达元素并获取焦点但顺序由平台决定、正值则表示以增值排序的方式获取焦点（如果值相同，则按照元素出现的先后顺序决定获取焦点的顺序）。在排序的键盘导航单上，如果一个元素的tabindex的值是一个0或者无效值或没有该属性，那么它应该被放在值是正数的element后边。
* title————有关元素的附加说明信息，一般鼠标移到标签上方时，信息会通过工具提示条显示出来。

# A
```
<a href="https://www.google.com">这是一个超链接</a>
```
创建一个到达其他网页、文件、同一页面内的位置、电子邮件地址或任何其他URL的超链接。
* download————此属性指示浏览器下载URL而不是导航到URL，因此将提示用户将其保存为本地文件。（HTML5）
* href————指定超文本链接来源。表示链接目标的URL或URL片段（URL片段是由一个hash符号(＃)，它指定一个内部目标在当前文档中的位置(ID)开头的名字）。
* hreflang————指定链接的资源所使用的人类语言（仅提供建议，并无内置功能）。
* rel————指定了目标对象到链接对象的关系。该值是空格分隔的列表类型值( https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types )。
* target————指定在何处显示链接的资源。 取值为标签（tab），窗口（window），或框架（iframe）等浏览上下文的名称或其他关键词。常用值包括：_self、_blank、_parent、_top。使用target时，考虑添加 rel="noopener norefferrer" 以防止针对 window.opener API 的恶意行为。
* type————指定在一个 MIME type 链接目标的形式的媒体类型（仅提供建议，并无内置功能）。
* 无障碍建议：锚点标签常常通过将 href 属性设置为 "#" 或 "javascript:void(0)" 来创造一个能阻止页面刷新的伪按钮的方式被滥用。 这些属性值会在拖动/复制链接时导致意外行为、在新窗口/新标签打开链接、加入书签以及JavaScript仍在下载时会出现错误或被禁用。这也会向辅助技术（如屏幕阅读器）传达不正确的语义。在这些情况下，推荐使用 BUTTON 来代替。通常情况下，您应该只将锚点用于正常的 URL 导航。 
* 注意事项：A 不能与 A 产生嵌套关系。否则会被解析成非嵌套关系。

# ABBR
```
<abbr title="Internationalization">I18N</abbr>
```
用于向搜索引擎解析这是一个缩写词并通过title属性提供完整的描述。
* 这个元素只有全局属性。
* 注意事项：在默认样式方面，一般的浏览器就会跟 SPAN 一样。Opera、Firefox和其他一些浏览器给这个元素的内容添加一条点状下划线 。一些浏览器不仅添加点状下划线，而且还把元素的内容添加小写大写字母的样式。为了避免这个样式，在CSS中添加font-variant: none 。

# ACRONYM
```
<acronym title="World Wide Web">WWW</acronym>
```
功能基本和 ABBR 一致。已过时，请使用 ABBR 代替。

# ADDRESS
```
<address>
    <p>Chris Mills, Manchester, The Grim North, UK</p>
    If you see any bugs, please <a href="mailto:webmaster@somedomain.com">contact webmaster</a>
</address>
```
用于描述文章编写者或网站拥有者(组织)的联系信息。内容可包括物理地址，URL，email地址，电话号码，社交媒体链接，地理坐标等待。
* 这个元素只有全局属性。
* 注意事项：ADDRESS 不能与 ADDRESS 产生嵌套关系。

# AREA
```
<img src="mm.jpg" alt="美女" usemap="#MM" width="256" height="191">
<map id="MM" name="MM">
    <area shape="rect" coords="20,20,80,80" href="#rect" alt="矩形">
    <area shape="circle" coords="200,50,50" href="#circle" alt="圆形">
    <area shape="poly" coords="150,100,200,120,180,130,190,180,150,150,100,160,140,120,100,110" href="#poly" alt="多边形">
</map>
```
结合 MAP 使用，用于为图片生成热点区域。
* 可在标签内使用href属性添加跳转超链接，这可以解决前面 A 元素不能与 A 元素产生嵌套关系这个问题（但在单纯的文字超链接中，必须用一张透明的图片覆盖到文字上面，以实现浏览器兼容）。
* alt———— MAP 所指向的图片不显示时出现的文字。当使用href属性时，该属性是必须的。
* coords————热点区域的坐标集合。形式(值的数量和意思)由shape属性决定。HTML5后，值不能是百分比，只能是像素值。
* download————此属性指示浏览器下载URL而不是导航到URL，因此将提示用户将其保存为本地文件。（HTML5）
* href————在HTML4中，要么href出现，要么nohref（HTML已废弃该属性）出现。在HTML5中，和 A 元素的意义一样。
* hreflang————指定链接的资源所使用的人类语言（仅提供建议，并无内置功能）。
* media————指定链接的资源的媒体类型（默认为all）。
* rel————指定了目标对象到链接对象的关系。该值是空格分隔的列表类型值( https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types )。
* shape————值包括了rect（矩形）、circle（圆形）、poly（多边形）。
* target————指定在何处显示链接的资源。取值为标签（tab），窗口（window），或框架（iframe）等浏览上下文的名称或其他关键词。常用值：_self、_blank、_parent、_top。使用target时，可添加 rel="noopener norefferrer" 以防止针对window.opener API的恶意行为。
* 注意事项：这个元素只能在 MAP 元素中使用（不必是直接子元素）。

# ARTICLE
```
<article class="film_review">
    <header>
        <h2>头部信息，通常是标题</h2>
    </header>
    <section class="main_review">
        <p>Dinos were great!</p>
        这里可以防止其他的 ARTICLE 元素<br/>
    </section>
    <!--这里可以放置更多的 SECTION 元素-->
    <footer>
        <p>Posted on <time datetime="2015-05-15 19:00">May 15</time> by Staff.</p>
  </footer>
</article>
```
用于表示文档、页面、应用或网站中的独立结构，其意在成为可独立分配的或可复用的结构。例如 论坛帖子、杂志或新闻文章、博客、用户提交的评论、交互式组件，或者其他独立的内容项目。
* 这个元素只有全局属性。
* 注意事项：
* 1、当 ARTICLE 元素嵌套使用时，则该元素代表与外层元素有关的文章（例如新闻与下面的评论就构成这种关系）。 
* 2、ARTICLE 元素的作者信息可通过 ADDRESS 元素提供，但是不适用于嵌套的 ARTICLE 元素。 
* 3、ARTICLE 元素的发布日期和时间可通过 TIME 元素的datetime属性表示（pubdate属性已废弃）。

# ASIDE
```
<article>
    <p>The Disney movie <cite>The Little Mermaid</cite> was first released to theatres in 1989.</p>
    <aside>
        <p>The movie earned $87 million during its initial release.</p>
    </aside>
    <p>More info about the movie...</p>
</article>
```
用于表示只与文档中主要内容间接相关的部分。该元素通常显示为侧边栏或导航栏。
* 这个元素只有全局属性。
* 注意事项：不要在圆括号中的文本中使用 ASIDE 标签，因为这种文本会被浏览器当做主要内容的一部分。

# AUDIO
```
<audio src="http://developer.mozilla.org/@api/deki/files/2926/=AudioTest_(1).ogg" autoplay>
    Your browser does not support the <code>audio</code> element.
</audio>
<audio controls="controls">
    Your browser does not support the <code>audio</code> element.
    <source src="foo.wav" type="audio/wav">
</audio>
```
用于向文档嵌入一个或多个声音内容。
* 嵌入的方式包括在 AUDIO 标签上使用src属性或包含 SOURCE 元素（如果两种方式均存在，浏览器会选择最合适的一种）。
* autoplay————如果该属性存在（即使值设置成了"false"），不用等全部加载完成，声音便会自动播放。
* buffered————通过该属性获取已缓冲的资源的时间段信息。该属性包含一个TimeRanges对象（对象包含length属性、start()方法、end()方法）。
* controls————如果该属性出现在标签中，浏览器便会为读者提供控制条（通常包括音量、进度拖动条、暂停/重播）。
* loop————如果指定了该属性，则声音自动在播放结束后重新播放。
* muted————"true"指定初始化时为静音，"false"指定初始化时为非静音。默认为"false"。
* played————一个TimeRanges对象，示所有已播放的音频片段。
* preload————"none"：指定声音不应当自动加载；"metadata"：指定只自动加载声音的元数据（例如声音长度信息）；"auto"：自动加载整个声音文件；""：跟"auto"一样。要注意的是，如果设置了autoplay属性，preload属性则无效。
* src————指定音频的URL（可选项）。你也可以通过在 AUDIO 标签块中嵌入一个 SOURCE 标签来指定声音源，从而替代src属性。
* volume————指定播放音量。范围是0.0(静音) - 1.0(最大音量)。
* 注意事项：
* 1、建议提供浏览器不支持音频播放时的替代内容。
* 2、时间偏移量目前是指定为float类型的值，表示偏移的秒数，但时间偏移量值的定义还没有完成，有可能会变更。
* 3、VIDEO 标签可以通过嵌入 TRACK 元素包含子标题和字幕，但 AUDIO 不可以。

# B
```
<b class="text_bold">这是加粗字体</b>
```
一个单纯的样式标签，指定文本要用粗体（用于吸引读者的注意）。
* 这个元素只有全局属性。
* 注意事项：如果是为了突出内容的重要性，那么建议使用 STRONG 代替。如果只是单纯为了加粗字体，才使用该标签（最好加以class属性来同时设置font-weight为"bold"值，以防止下一版本废弃该标签）。

# BASE
```
<base target="_blank" href="http://www.example.com/">
```
用于指定所在文档的所有相对URL路径的基本URL路径。
* 如果需要在JS代码中获取该路径，可以通过document.baseURI拿到。
* href————如果设置了该属性，那本元素必须放置在其他带有URL值的元素之前。该属性值允许绝对路径和相对路径。
* target————为没有使用target引用属性的元素指定一个名字或关键字，当元素的超链接或导致导航的形式被激活时，指定显示结果的默认位置（例如标签页，窗口或者内联框）。常用值包括：_self、_blank、_parent、_top。
* 注意事项：
* 1、一个文档只能拥有一个 BASE 元素（如果设置了多个，则只是第一个有效，其余的会被忽略）。
* 2、OpenGraph元标签不认识 BASE 标签，因此需要一直使用全路径。

# BDO
```
<bdo dir="rtl">感谢您对HTML的支持</bdo>
```
用于解析dir属性，即修改文字的方向。
* dir————值有两个："ltr"，文字从左到右；"rtl"，文字从右到左。
* 注意事项：HTML4不支持对 BDO 标签添加事件监听器。

# BLOCKQUOTE
```
<blockquote cite="http://developer.mozilla.org">
    <p>This is a quotation taken from the Mozilla Developer Center.</p>
</blockquote>
```
用于表示其中的文字是引用内容。若引文来源于网络，则可以将原内容的出处 URL 地址设置到 cite 特性上。
* 通常在渲染时，这部分的内容会有一定的缩进。可以使用CSS中的margin属性来改变 BLOCKQUOTE 的缩进。
* cite————指定一个标注引用的信息的来源文档或者相关信息的URL。通常用来描述能够解释引文的上下文或者引用的信息。
* 注意事项：如果想要使用短引用（行间引用），可以使用 Q 标签。若要以文本的形式告知读者引文的出处（引用出处）时，可以通过 CITE 元素。

# BODY
```
<html>
    <head>
        <title>Document title</title>
    </head>
    <body onunload="onUnloadCallback">
        <p>This is a paragraph</p>
    </body>
</html>
```
用于表示一个HTML文档的内容。
* 一个文档只能拥有一个 BODY 标签，而且必须是 HTML 标签的第二个元素。
* 可以通过document.body访问该元素。
* onafterprint————指定用户打印完本文档完成后的回调函数。
* onbeforeprint————指定用户请求打印完本文档时的回调函数。
* onbeforeunload————指定本文档将要卸载时的回调函数。
* onblur————指定本文档失去焦点时的回调函数。
* onerror————指定本文档加载出现错误时的回调函数。
* onfocus————指定本文档获取焦点时的回调函数。
* onhashchange————指定本文档的url地址的hash值变化时的回调函数。
* onload————指定本文档加载完成时的回调函数。
* onmessage————指定本文档在收到一份消息时的回调函数。
* onoffline————指定本文档在网络通信失败时的回调函数。
* onpopstate————指定本文档在用户变更session历史导航记录(前进或后退)时的回调函数。
* onredo————指定本文档在用户前进(历史记录)时的回调函数。
* onresize————指定本文档在浏览器窗口大小发生变化时的回调函数。
* onstorage————指定本文档在存储区发生改变时的回调函数。
* onundo————指定本文档在用户后退(历史记录)时的回调函数。
* onunload————指定本文档在页面卸载时的回调函数。

# BR
```
<br>
```
用于文本换行（相当于回车键）。
* 这个元素只有全局属性。
* 注意事项：如果只是单纯的为了增加文本段落之间的间隔，不要用 BR ，而应当用margin属性来实现。

# BUTTON
```
<button type="submit" name="myButton" value="foo">Click me</button>
```
表示一个可点击的按钮。可用于表单或者其他需要按钮的地方。
* 默认情况下，按钮会呈现与用户主机相似的样式，基于user agent。
* autofocus————指定当页面初始化时按钮必须自动获得输入焦点（只有一个表单关联元素可以指定该属性）。(HTML5)
* disabled————当值为"true"时，用户不能与该按钮交互。若该属性没有设置，则从 FIELDSET 等包含元素中继承。默认值为"false"。
* form————指定本按钮所属的 FORM 标签（值就是 FORM 的id）。若不设置该属性，则按钮归属于父级的 FORM 元素。因此设置了该属性可以让 BUTTON 元素出现在页面的任何位置。(HTML5)
* formaction————表示程序处理 BUTTON 提交信息的URI。此属性将重写 BUTTON 所在表单的action属性。(HTML5)
* formenctype————若按钮是提交类型，则指定所属表单提交时所使用的文本格式。常用值有："application/x-www-form-urlencoded"(默认值)、"multipart/form-data"(提交的内容含文件类型时使用)、"text/plain"。此属性将重写 BUTTON 表单拥有者的enctype属性。(HTML5)
* formmethod————若按钮是提交类型，则指定所属表单提交时所使用的HTTP方法。常用值有："post"、"get"。此属性将重写 BUTTON 表单拥有者的method属性。(HTML5)
* formnovalidate—————若按钮是提交类型，则指定所属表单提交时不进行验证。此属性将重写 BUTTON 表单拥有者的novalidate属性。(HTML5)
* formtarget————若按钮是提交类型，则指定所属表单提交时在何处显示返回结果。常用值有："_self"、"_blank"、"_parent"、"_top"。此属性将重写 BUTTON 表单拥有者的target属性。(HTML5)
* name———— BOTTON 的名称，将与表单数据一起提交到服务器。
* type———— BOTTON 的类型，包括 "submit"(默认值。将表单数据提交到服务器)、"reset"(重置表单所有组件为初始值)、"button"(没有默认行为)。
* value———— BOTTON 的初始值，它定义的值与表单数据的提交按钮相关联。与name数值组成一对键值对，当表单中的数据被提交时，这键值对会被一起递送至服务器。
* 注意事项：
* 1、BUTTON 和 INPUT 都能成为按钮。但 BUTTON 能内嵌其他元素，并更容易修改样式（包括可以使用 :before 和 :after 伪类）。而 INPUT 只有文本值属性。
* 2、IE7有一个BUG，是关于提交按钮的。以上面的代码为例，将被发送的数据是 myButton=Click me 而非 myButton=foo 。
* 3、IE6就更多BUG了。除了会搞错submit按钮的键值对，还会出现点击一个表单中的提交按钮，其他表单也会发生提交的情况。
* 4、火狐浏览器同样有几个特殊情况：::-moz-focus-inner样式设置了按钮获得焦点时出现小点边框(可通过修改该伪类的样式重置)、按钮动态变成disabled后刷新不能恢复可点击状态(可通过设置autocomplete属性为off来解决)、低于35版本的安卓版会默认设置了background-image渐变(可通过设置按钮的样式属性background-image为none来重置)。

# CANVAS
```
<canvas id="canvas" width="300" height="300">
    <p>你的浏览器不支持画布哦</p>
</canvas>
```
用于显示脚本（包括canvas脚本和webgl脚本）绘制的图形与动画。
* height————指定画布的高度值，单位是像素。默认值为150。
* width————指定画布的宽度值，单位是像素。默认值为300。
* 注意事项：
* 1、建议提供浏览器不支持画布或禁用了JavaScript时的替代内容。
* 2、与 IMG 标签不同，CANVAS 标签必须提供闭合标签。
* 3、可以通过css样式来改变 CANVAS 的大小。但如果画布因此出现模糊的情况，则应当只设置 CANVAS 的width和height属性来确定画布的大小。
* 3、如果画布不需要使用透明度，则可以告诉浏览器该画布是非透明的以优化渲染效率。即将  var ctx = canvas.getContext('2d');  修改成  var ctx = canvas.getContext('2d', { alpha: false });  。

# CAPTION
```
<table>
    <caption>这是表格的标题</caption>
    <tr>
        <th>表头 1</th>
        <th>表头 2</th>
    </tr>
    <tr>
        <td>表项 1</td>
        <td>表项 2</td>
    </tr>
</table>
```
用于 TABLE 元素上的标题（说明文字）。
* 它的样式以及相对于表格的位置可以通过css的属性caption-size和text-align改变（不要再使用 CAPTION 的属性align）。
* 注意事项：如果 TABLE 元素是 CAPTION 的父元素，而 CAPTION 又是 FIGURE 元素的唯一后代时，则应当使用 FIGCAPTION 元素替代 CAPTION 元素。

# CITE
```
<p>More information can be found in <cite>[ISO-0000]</cite>.</p>
```
用于描述一个被引用的作品的相关信息，必须包含有该作品的标题或URL。相关信息也可能是一个根据合适的上下文的相关引用元数据而约定的简写形式。
* 这个元素只有全局属性。
* 注意事项：
* 1、可以被引用的具有创造性的作品包括：一本书、一份研究论文、一篇文章、一首诗、一篇乐谱、一首歌、一份戏剧或电影剧本、一部电影、一集电视剧、一场游戏、一座雕像、一幅画、一则戏剧作品、一场话剧、一部歌剧、一张唱片、一场展览、一份法律案例报告、一份计算机程序、一个网站、一张网页、一次推文或评论、一次论坛推文或评论、一篇Twitter上的推文、一篇Facebook上的推文、一次书面或口头上的陈述 等等。
* 2、值得注意的是，W3C规范所说的与创造性的作品相关的信息，可能包括了作品的作者名称。但是，WHATWG规范的说法则相反：任何时候、任何情况下，CITE 都不应当包含一个人的名字。
* 3、应当在 BLOCKQUOTE 元素或 Q 元素上使用cite属性来标明所引用的材料。
* 4、CITE 元素的默认样式是font-style为italics。可以通过css设置font-style来重置该样式。

# CODE
```
<p>The function <code>selectAll()</code> highlights all the text in the input field so the user can, for example, copy or delete the text.</p>
```
呈现一段计算机代码。默认情况下，它以浏览器的默认等宽字体显示。
* 这个元素只有全局属性。
* 注意事项：css规则可以覆盖浏览器默认的 CODE 标签字体样式。但用户设置的浏览器字体选项可能会超过css的优先级，使之无效。

# COL
```
<table>
    <colgroup>
        <col style="background-color: #0f0">
        <col span="2">
    </colgroup>
    <tr>
        <th>Lime</th><!--该项会显示绿色背景-->
        <th>Lemon</th>
        <th>Orange</th>
    </tr>
    <tr>
        <td>Green</td><!--该项会显示绿色背景-->
        <td>Yellow</td>
        <td>Orange</td>
    </tr>
</table>
```
定义一个表格中的一列，并用于定义所有公共单元格上的公共语义。通常位于 COLGROUP 标签中。
* 此元素允许使用CSS进行样式列，但只有少数属性将对该列产生影响。
* span————值为一个正整数，指定 COL 连续跨了多少列。默认值为"1"。
* 注意事项：
* 1、不要幻想在 COL 上声明css的text-align属性，因为 TD 元素并不是 COL 标签的子元素，因此 TD 并不能从 COL 上继承text-align属性。
* 2、关于同一列的text-align属性，可以通过css伪类:nth-child(an+b)来实现，如：td:nth-child(2) { text-align: right; }。
* 3、关于同一列的text-align属性，如果 TABLE 里面（的 TD ）有设置colspan属性为n，也可以通过 td[colspan=n] { text-align: right; } 来实现。

# COLGROUP
```
<table>
    <colgroup>
        <col style="background-color: #0f0">
        <col span="2">
    </colgroup>
    <tr>
        <th>Lime</th><!--该项会显示绿色背景-->
        <th>Lemon</th>
        <th>Orange</th>
    </tr>
    <tr>
        <td>Green</td><!--该项会显示绿色背景-->
        <td>Yellow</td>
        <td>Orange</td>
    </tr>
</table>
```
用于在一个表格里面定义一组列。
* span————值为一个正整数，指定 COLGROUP 连续跨了多少列（如果 COLGROUP 里面有一个或多个 COL 标签，则此属性无效）。默认值为"1"。
* 注意事项：和 COL 元素一样。

# CONTENT
已废弃，请用 SLOT 元素代替。

# DATA
```
<p>新产品</p>
<ul>
    <li><data value="3967381398">迷你番茄酱</data></li><!--value是该产品的39码-->
    <li><data value="3967381399">巨无霸番茄酱</data></li><!--value是该产品的39码-->
    <li><data value="3967381400">超级巨无霸番茄酱</data></li><!--value是该产品的39码-->
</ul>
```
用于将给定内容关联到一个机器可读的翻译数据。（属于HTML5新增标签）
* 如果该内容是与时间或日期相关的，则应当使用 TIME 元素。
* value————该属性指定元素内容对应的机器可读的翻译。

# DATALIST
```
<label>
    Choose a browser from this list: 
    <input list="browsers" name="myBrowser" />
</label>
<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Internet Explorer">
    <option value="Opera">
    <option value="Safari">
    <option value="Microsoft Edge">
</datalist>
```
用于包含一个 OPTION 元素组成的集合，以提供其他表单可选值。
* 这个元素只有全局属性。
* 注意事项：该标签只在IE10以上的浏览器支持，为了提高兼容性，使用时应加入Polyfill：https://github.com/mfranzke/datalist-polyfill 。

# DD
```
<dl>
    <dt>Firefox</dt>
    <dd>A free, open source, cross-platform, graphical web browser</dd>
    <!-- other terms and definitions -->
</dl>
```
用于指明一个描述列表 DL 元素中一个术语的描述。
* nowrap————"yes"表示描述文本不会被包裹。默认值为"no"。（此属性为非标准属性）
* 注意事项：该元素只能作为 DL 元素的子元素出现，并且必须跟着一个 DT 元素。

# DEL
```
<p><del>This text has been deleted</del>, here is the rest of the paragraph.</p>
<del><p>This paragraph has been deleted.</p></del>
```
用于展示文档中被删除了的文本。（元素 INS 则恰好相反：用户标识文档中新增的文本）
* 在样式上，这个元素通常会被渲染上一根划过的线。
* cite————指定一个解释该变化的源头的URI。
* datetime————指定变化的日期以及时间。值必须是一个有效的日期时间字符串。

# DETAILS
```
<details>
    <p>这里没有指定摘要或标签信息，因此标签会使用浏览器提供的默认信息：英文是"Details"，中文则是"详细信息"。</p>
</details>
<details>
    <summary>这是摘要</summary>
    <p>这里提供了摘要信息，因此详情闭合时，本小部件显示的是 SUMMARY 所提供的文本："这是摘要"。</p>
</details>
<details open>
    <summary>这是摘要</summary>
    <p>本小部件指定了open属性，因此会自动展开，并显示这段文本。</p>
</details>
```
用于创建一个公开更多内容的小部件（当该小部件的状态变成"open"时，更多的信息才可见）。
* 标签会提供一个三角形用于改变小部件的显示状态。可以通过 SUMMARY 元素提供摘要或标签信息。
* 如果 DETAILS 标签的第一个元素是 SUMMARY 的话，该 SUMMARY 的内容将会被用作小部件的标签信息(label)。
* open————指定是否显示详情。默认值为"false"，即 DETAILS 不可见。（相应的DOM事件名称为"toggle"）
* 注意事项：现在有一个bug，即 DETAILS 带有css的animation值的时候，改变open属性是无法打开详情的。

# DFN
```
<p><strong>HTML定义元素</strong>(<strong><dfn id"definition-dfn">&lt;dfn&gt;</dfn></strong>)用于指定一个定义语句或段落的被定义术语。</p>
<p>你可以通过点击<code><a href="#definition-dfn">&lt;dfn&gt;</a></code>元素跳到相应词条的解析。</p>
<p><dfn><abbr title="Hubble Space Telescope">HST</abbr></dfn>是指美国宇航局发射的在轨超过了20年的太空探测科学装备。</p><!--这是定义也语句-->
<p><abbr title="Hubble Space Telescope">HST</abbr>比之前发射的其他深空探测装备先进很多。</p><!--这不是定义也语句-->
```
用于指定一个定义语句或段落的被定义术语。 DFN 元素的最近祖先标签包括了 P 标签、DT/DD 标签对、SECTION 标签，这些标签用于包裹对 DFN 含有的被定义术语的解析。
* 从功能上说，该标签没有太大的作用。（主要目的就是为了使文档更符合语义化）
* title————该属性比较特殊：当该标签内是一个缩列词时，值可以是缩列词的完整形式，因此值就是被定义术语；当标签内的词有一个单独的子元素 ABBR 时(连其他文本也没有)，ABBR 上的title属性值就是被定义术语；否则，DFN 标签上的文本就是被定义术语。若 DFN 包含了本属性，则 DFN 必须只含有被定义的术语，而不能其他文本。
* 注意事项：
* 1、如果 DFN 上有id属性，那么你可以通过 A 标签来连接该 DFN 元素。这样的连接可以用于帮助读者快速导航到术语的定义之处（为 A 标签指定href="#id"，使其能跳转到 DNF 标签的位置）。
* 2、被定义术语的具体值需根据title属性及其标签包含的内容决定：DFN 标签有title属性，那么被定义术语就是该title属性的值；若 DFN 标签包含有 ABBR 元素且 ABBR 元素含有title属性，则被定义术语是 ABBR 元素上的title属性的值；否则，被定义术语就 DFN 包含的文本。

# DIALOG
```
<!-- Simple pop-up dialog box, containing a form -->
<dialog open id="favDialog">
    <form method="dialog">
        <section>
            <p>
                <label for="favAnimal">Favorite animal:</label>
                <select id="favAnimal">
                    <option></option>
                    <option>Brine shrimp</option>
                    <option>Red panda</option>
                    <option>Spider monkey</option>
                </select>
            </p>
        </section>
        <menu>
            <button id="cancel" type="reset">Cancel</button>
            <button type="submit">Confirm</button>
        </menu>
    </form>
</dialog>
<menu>
    <button id="updateDetails">Update details</button>
</menu>
<script>
(function() {
    var updateButton = document.getElementById('updateDetails');
    var cancelButton = document.getElementById('cancel');
    var favDialog = document.getElementById('favDialog');
    // Update button opens a modal dialog
    updateButton.addEventListener('click', function() {
        favDialog.showModal();
    });
    // Form cancel button closes the dialog box
    cancelButton.addEventListener('click', function() {
        favDialog.close();
    });
})();
</script>
```
用于展示一个对话盒子或其他交互组件，例如一个监视器或窗口。
* 现阶段除了Chrome和Opera，其他浏览器均不支持，因此，如果需要使用，应当引入一下Polyfill： https://github.com/GoogleChrome/dialog-polyfill 。
* open————指定对话框是否处于活跃状态或是否可用于交互。但该属性没有设置时，对话框不应当对用户显示。
* 注意事项：
* 1、DIALOG 元素一定不要使用tabindex属性。
* 2、FORM 元素可以被结合到一个对话框内，只需要为 FORM 元素指定一个属性method="dialog"即可。当这样一个表单被提交时，对话框将会被关闭，同时 DIOLOG 的属性returnValue会被设置成提交按钮的value值。
* 3、DIALOG 元素的css伪类::backdrop可以被样式化，例如在对话框处于活跃状态时使不可访问的内容变得灰暗。

# DIV
```
<div id="textBox">
    <p>Any kind of content here. Such as &lt;p&gt;, &lt;table&gt;. You name it!</p>
    <p>Some other text here.</p>
</div>
```
用于流内容的一般性容器。
* 默认不设置任何样式。
* 其使用目的不是用来展示任何东西，而是作为内容的分组以便于应用class、id、lang等属性。
* 这个元素只有全局属性。
* 注意事项：DIV 元素只应在完全找不到合适的语义化标签（例如 ARTICLE 或 NAV ）时才使用。

# DL
```
<dl>
    <dt>Name</dt>    
    <dd>Godzilla</dd>
    <dt>Born</dt>
    <dd>1952</dd>
    <dt>Birthplace</dt>
    <dd>Japan</dd>
    <dt>Color</dt>
    <dd>Green</dd>
</dl>
<dl>
    <!--这样使用便于样式化每一组数据-->
    <div>
        <dt>Name</dt>
        <dd>Godzilla</dd>
    </div>
    <div>
        <dt>Born</dt>
        <dd>1952</dd>
    </div>
    <div>
        <dt>Birthplace</dt>
        <dd>Japan</dd>
    </div>
    <div>
        <dt>Color</dt>
        <dd>Green</dd>
    </div>
</dl>
```
用于展示一个个描述内容所组成的列表。
* 该元素包含了一系列的术语（通常使用 DT 标签）与描述（通常使用 DD 标签）的组合。通常用于实现一个词汇表或展示元数据（一个键值对所组成的列表）。
* 这个元素只有全局属性。
* 注意事项：根据语义化的原则，不要拿 DL 或 UL 元素仅仅用于实现内容的在页面的缩进（应当通过css样式来实现）。

# DT
```
<dl>
    <dt>Firefox</dt>
    <dd>A free, open source, cross-platform, graphical web browser</dd>
    <!-- other terms and definitions -->
</dl>
```
用于指定一个描述或定义列表的术语。
* 这个元素只有全局属性。
* 注意事项：
* 1、该元素只能作为 DL 元素的子元素出现，并且需要出现在 DT 元素或者 DD 元素之前。
* 2、多个 DT 元素出现在同一行则意味着它们都被接下来的 DD 元素所定义。

# EM
```
<p>
    In HTML 5, what was previously called <em>block-level</em> content is now called <em>flow</em> content.
</p>
```
用于标记需要强调(突出)的文本。（EM 元素可以相互嵌套，内部的 EM 标签包含的文本的强调等级比外部的更高）
* 该元素主要用在语句某个词上以改变句子的侧重（通常意味着话中有话，人或软件在读该词时，会提现一种强调的语气）。
* 这个元素只有全局属性。
* 注意事项：
* 1、通常该元素会将包含的文字样式化为斜体。但不应当仅仅为了将文字斜体化而用该标签，你应当用css样式来达到样式化的目的。
* 2、将文字样式化为斜体的也包括 CITE 元素，但应当在标记一份作品的标题才使用 CITE 元素（这时则不应当使用 EM 元素）。
* 3、与 EM 相对是 STRONG 元素。但 STRONG 元素只用于标记比周围其他文本更具重要性(是内容的绝对重点)的文本。
* 4、EM 元素常常用于指示一个含蓄或者明确的对比。
* 5、和 I 标签的比较：EM 标签压力强调其包含的内容；I 标签则表示从正常的散文中区分出的文本，一个外来词(通常有别于文本主要语言)，虚构的人物思考，或者当文本指的是一个词的定义而不是其本身代表的语义。如果是电影或书籍的名字，则应当使用 CITE 标签。

# EMBED
```
<embed type="video/quicktime" src="movie.mov" width="640" height="480">
```
用于在文档中特点的位置嵌入外部的内容。
* 外部的内容由外部的软件或其他可交互的内容来源(例如浏览器插件)提供。
* width————资源展示的宽度。（只支持绝对值如像素，不支持百分比）
* height————资源展示的高度。（只支持绝对值如像素，不支持百分比）
* src————被嵌入的资源的URL。
* type————通过指定MIME类型来告诉浏览器实例化时所需要的插件。
* 注意事项：
* 1、大多数现代浏览器已经弃用并取消了对浏览器插件的支持，所以如果您希望您的网站可以在普通用户的浏览器上运行，那么依靠 EMBED 通常是不明智的。
* 2、不同浏览器之间显示有差异。Blink内核浏览器（Chrome，Opera）会显示HTML资源的内容，但Firefox会显示一条通知消息，指出内容需要一个插件。建议使用 OBJECT 或 IFRAME 元素。

# FIELDSET
```
<form action="test.php" method="post">
    <fieldset>
        <legend>标题</legend>
        <input type="radio" id="radio">
        <label for="radio">点我</label>
    </fieldset>
</form>
```
用于在一个网页表单里面将几个控件(controls)以及标签(labels)划分为一组。
* disabled————如果设置了该属性，则其后代表单控件（除了它的第一个可选的 LEGEND 子元素），将被禁用(如不能编辑、无法接收鼠标点击或聚焦的相关事件、控件变灰等)。(HTML5)
* form————用于关联 FORM 元素的id属性。默认值为最近的 FORM 祖先标签的id属性值。(HTML5)
* name————分组相关的名称(name)。(HTML5)
* 注意事项：
* 1、不像其他元素，WHATWG的HTML解析规范建议为 FIELDSET 元素设置的默认样式应包括属性"min-width: min-content;"。很多浏览器实现了这一点。
* 2、使用 FIELDSET 元素会形成一个新的块级上下文。
* 3、在IE11中，并不是所有在设置了禁用属性的 FIELDSET 元素中的表单控件都会合适地被禁用：例如input[type="file"]在设置了禁用的 FIELDSET 中就不被禁用，input[type="text"]也可以继续编辑。

# FIGCAPTION
```
<figure>
    <figcaption><cite>Edsger Dijkstra :-</cite></figcaption>
    <p>"If debugging is the process of removing software bugs,<br />then programming must be the process of putting them in"</p>
</figure>
```
用于标记一句与一副图像或一则说明(插画)（图像、插画、说明通常跟随在 FIGCAPTION 标签后面）相关的说明/标题，FIGURE 标签就是 FIGCAPTION 标签的直接父元素。
* 这意味着 FIGCAPTION 标签在 FIGURE 块里是第一个或最后一个子元素。同时 FIGCAPTION 元素是可选的；如果没有该元素，这个父节点的图片只是会没有说明/标题。
* 这个元素只有全局属性。

# FIGURE
```
<!-- Just a figure -->
<figure>
    <img src="https://developer.cdn.mozilla.net/media/img/mdn-logo-sm.png" alt="An awesome picture">
</figure>
<p>这是文件流的一部分。</p>
<!-- Figure with figcaption -->
<figure>
    <img src="https://developer.cdn.mozilla.net/media/img/mdn-logo-sm.png" alt="An awesome picture">
    <figcaption>MDN Logo</figcaption>
</figure>
<p>这也是文件流的一部分。</p>
```
用于表示一段独立的内容，通常带有一个标题(caption)，并且作为一个独立的引用单元。（标题包含在 FIGCAPTION 中）
* 这个元素只有全局属性。
* 注意事项：
* 1、当它属于主体(main flow)时，它的位置独立于主体。这个标签经常是在主文中引用的图片、插图、表格、代码段等等，当这部分转移到附录中或者其他页面时不会影响到主体。
* 2、作为一个分片内容的根，FIGURE 元素内容的纲要是被文档的主纲要排除在外的。

# FOOTER
```
<footer>
    Some copyright info or perhaps some author info for an &lt;article&gt;?
</footer>
```
用于表示离本元素最近的分片内容或分片内容的根的页脚。本标签通常包含所在分片的作者、版权数据或文档的相关链接。
* 这个元素只有全局属性。
* 注意事项：
* 1、FOOTER 元素中的有关于作者的信息应当包含在 ADDRESS 标签中。
* 2、FOOTER 元素并不属于分片内容，因此不会为文档纲要引入一个新的章节。

# FORM
```
<!-- Simple form which will send a POST request -->
<form action="" method="post">
    <label for="POST-name">名字：</label>
    <input id="POST-name" type="text" name="name">
    <input type="submit" value="保存">
</form>
```
用于表示一个包含有可交互控件并能提交数据到一个网络服务器的文档部分。
* 可以对 FORM 元素应用:valid和:invalid这几个css伪类。
* accept-charset————指定服务器接受的一个字符编码列表(用空格或逗号隔开)。默认值为"UNKNOWN"，即参考所在文档的字符编码。HTML5以前，字符编码项可以用空格或逗号隔开，HTML5以后，只允许用空格隔开。
* autocomplete————指定输入框元素是否默认被浏览器自动完成值的填写（当然，这个设定会被输入框本身的autocomplete属性值所覆盖）。有两个值。"off"：指定用户在每次使用输入框时，都必须明确地输入值，又或者文档本身提供自己的自动完成方法（浏览器是不会自动完成输入的）。"on"：浏览器会根据用户以前在改输入框中输入的内容，自动将其输入填充到输入框中。(html5)
* enctype————当method属性被设置成"post"时，enctype就是用于指定要提交到服务器的表单的内容的MIME类型。常用值有："application/x-www-form-urlencoded"(默认值)、"multipart/form-data"(提交的内容含文件类型时使用)、"text/plain"。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formenctype属性覆盖。
* method————浏览器提交表单的HTTP方法。常用值有："post"(对应HTTP的"POST"方法。表单数据将被包含在表单体中，然后发送给服务器)、"get"(对应HTTP的"GET"方法。表单数据将附在要请求URI的查询位置中，即"?"后面，然后发送给服务器。这种方式要求表单没有副作用，并且数据需要进行URI编码)。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formenctype属性覆盖。
* name————表单的名称(name)。
* novalidate————指定表单在提交时是否不要做验证。不指定该属性的情况下，表单是会被验证的。默认的设置可以被 BUTTON 和 INPUT 元素设置的formnovalidate属性覆盖。(html5)
* target————值为一个名称或关键词，用来指定在何处显示提交表单后收到的返回信息。常用值有："_self"、"_blank"、"_parent"、"_top", 标签 IFRAME 的name属性值。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formtarget属性覆盖。
* 注意事项：
* 1、对于大多数浏览器来说，设置autocomplete属性并不会阻止浏览器询问用户是否想保存密码(包括用户名和密码)到本地的行为。如果用户同意了浏览器的存储密码的询问，则浏览器会在用户下次访问该网页时自动填充登录所需要的信息。
* 2、如果是由于文档本身提供了自己的自动完成方法而使你设置 FORM 元素的autocomplete属性为"off"，那么你也应当为表单中的每一个输入框设置autocomplete属性为"off"。
* 3、对于谷歌的Chrome浏览器来说，如果只在表单设置了autocomplete为"off"，但输入框没设置，则浏览器会提示说"该表单禁用了自动完成功能"。因此，最好对每个输入框都设置自定义的autocomplete属性，以增强用户体验。

# H1
# H2
# H3
# H4
# H5
# H6
```
<h1>Heading level 1</h1>
<h2>Heading level 2</h2>
<h3>Heading level 3</h3>
<h4>Heading level 4</h4>
<h5>Heading level 5</h5>
<h6>Heading level 6</h6>
```
分别用于表示章节标题的六个层级。H1 是最高章节等级，而 H6 则是最低章节等级。
* 这些元素只有全局属性。
* 注意事项：
* 1、标题信息可能会被用户代理使用：例如用来为文档自动构建一个内容的表格。
* 2、不要因为缩减标题字体大小而使用低等级的标题标签（应当通过设置css属性font-size来达到这个目的）。
* 3、避免跨等级使用标题标签：应当总是从 H1 开始，然后使用 H2 ，如此类推。
* 4、使用 SECTION 元素的时候，为了方便起见你应该考虑着去避免重复在一个页面上使用 H1 。
* 5、H1 应该用来表示页面的标题，其他的标题当从 H2 开始。 使用 SECTION 元素的时候，应当在每个 SECTION 中都使用一个 H2 。

# HEAD
```
<html>
    <head>
        <title>Document title</title>
    </head>
</html>
```
用于为文档提供通用信息（例如元数据），包括了文档的标题、样式与脚步的链接等。
* 这个元素只有全局属性。
* 注意事项：
* 1、如果在文档中省略了 HEAD 元素，现代的兼容HTML5的浏览器会自动为文档构建一个。（旧版的浏览器不支持这一点）

# HEADER
```
<!--属于页面的 HEADER -->
<header>
    <h1>Main Page Title</h1>
    <img src="mdn-logo-sm.png" alt="MDN logo">
</header>
<!--属于章节的 HEADER -->
<article>
    <header>
        <h2>The Planet Earth</h2>
        <p>Posted on Wednesday, 4 October 2017 by Jane Smith</p>
    </header>
    <p>We live on a planet that's blue and green, with so many things still unseen.</p>
    <p><a href="https://janesmith.com/the-planet-earth/">Continue reading....</a></p>
</article>
```
用于展示介绍性的内容，通常是一组介绍性或导航性的帮助。
* 该元素可能包含一些标题元素，也可能包括其他的例如一个图标、一个搜索表单、一个作者的姓名等等。
* 这个元素只有全局属性。
* 注意事项：
1、HEADER 元素不属于分片内容，因此不会为文档纲要引入一个新的章节。（也就是说，一个 HEADER 元素常常会被用来包含周围章节的标题(H1-H6元素)，但这并不是必须的）

# HR
```
<p>This is the first paragraph of text.</p>
<hr>
<p>This is the second paragraph of text.</p>
```
用于在段落层级元素之间显示主题性的隔离。（例如一个故事的场景变换、一个话题的主题改变）
* 历史上，这个元素会生成一根水平线（现在可能也会）。但这个元素由于被赋予了语义化功能，所以，如果你仅仅是希望画一根水平线，可以考虑用css样式来实现。
* 这个元素只有全局属性。

# HTML
```
<!DOCTYPE html>
<html>
    <head>...</head>
    <body>...</body>
</html>
```
用于表示一个HTML文档的根(最高层级元素)。所有其他元素都必须是 HTML 元素的后代。
* xmlns————指定文档的XML命名空间，默认值是 "http://www.w3.org/1999/xhtml" 。在XML解析器中，这个属性是必须的；在TEXT/HTML文档中，这个则是可选的。

# I
```
<p>The Latin phrase <i class="latin">Veni, vidi, vici</i> is often mentioned in music, art, and literature.</p>
```
用于标记一些从正常文本中分离出来的词，例如：技术名词、外语单词或者虚构的人物思考。通常以斜体的方式显现。
* 这个元素只有全局属性。
* 注意事项：
* 1、在早期的HTML规范中，I 标签仅仅是一个用于展示斜体字的元素（这很像 B 标签只用来展示粗体字一样）。现在不是了，它被赋予了更多的语义化作用。
* 2、在下面这些标签的语义都不合适的时候，再考虑使用 I 标签。
    * 使用 EM 标签来表示强调或者压力；
    * 使用 STRONG 标签来表示重要性；
    * 使用 MARK 标签来表示相关性；
    * 使用 CITE 标签来表示作品(例如一本书、一则戏剧或一首歌)的名称；
    * 使用 DFN 标签来表示一个术语的定义实例。
* 3、用class属性来指出该元素为何被使用是一个好的做法。毕竟 I 标签现在不一定需要显示成斜体，程序员可以修改它的样式。

# IFRAME
```
<iframe src="https://mdn-samples.mozilla.org/snippets/html/iframe-simple-contents.html" title="iframe example 1" width="400" height="300">
    <p>Your browser does not support iframes.</p>
</iframe>
```
用于展示一个嵌入(在本文档中)的一个浏览上下文。（事实上，就是本页面中嵌套另外一个HTML页面）
* 每一个浏览上下文都有它自己的session历史记录以及活跃文档。包含了嵌套内容的浏览上下文被称为父级浏览上下文。顶级浏览上下文(不再有父级)则通常是浏览器window本身。
* allowfullscreen————当该属性被设置为"true"时，可以同过元素的 Element.requestFullscreen() 方法将 IFRAME 标签所包含的页面扩展为全屏。（如果该属性不被设置，则元素无法进入全屏模式）
* allowpaymentrequest————如果一个跨域的 IFRAME 元素应当被允许调用支付请求的API的话，那么该属性应当被设置为"true"。
* height————指定 IFRAME 元素的高度（只支持像素单位）。
* name————被嵌入的浏览上下文的名字(name)。其值可用于 A 标签、FORM 标签、BASE 标签的target属性值，也可用于一个 INPUT 标签或 BUTTON 标签的formtarget属性的值。其值甚至可用于window.onpen()方法的windowName参数。
* sandbox————这是一个HTML5新增属性。当设置了该属性时，可以放开一些对iframe的限制。默认值为空字符串，即 IFRAME 会应用所有限制。值可以包含多个（用空格隔开）：
    * 1、allow-forms：允许嵌入的浏览上下文提交表单。
    * 2、allow-modals：允许嵌入的浏览上下文打开模态框（包括 alert，confirm，prompt ）。
    * 3、allow-orientation-lock：允许嵌入的浏览上下文拥有禁用锁住屏幕方向的能力（比如智能手机的水平朝向和垂直朝向）。
    * 4、allow-pointer-lock：允许嵌入的浏览上下文使用鼠标锁的相关接口（Pointer Lock API）。
    * 5、allow-popups：允许弹出窗口（例如 window.opne，target="_blank"，showModalDialog 等）。如果没设置该值，则嵌入的浏览上下文在使用这些方法时，会静默失败。
    * 6、allow-popups-to-escape-sandbox：允许一个沙盒内的文档打开新的窗口，并且不强制要求新窗口设置沙箱标记。（例如，这将允许一个第三方的沙箱环境运行广告开启一个登陆页面，新页面不强制受到沙箱相关限制）
    * 7、allow-presentation：允许嵌入者控制 IFRAME 是否启用一个展示会话。
    * 8、allow-same-origin：允许(IFRAME元素的)内容被看待为同源的（即跟父级文档的正常来源一样）。
    * 9、allow-scripts：允许浏览上下文运行脚本（但不能创建弹出窗口）。
    * 10、allow-top-navigation：允许嵌入的浏览上下文导航（加载）内容到顶级浏览上下文。
    * 11、allow-top-navigation-by-user-activation：允许当某个用户动作产生后，嵌入的浏览上下文导航（加载）内容到顶级浏览上下文。
    * 注1、当嵌入的文档与主页面是同源时，强烈不建议同时使用allow-scripts与allow-same-origin。（因为那样会允许嵌入的文档通过程序的方式移除sandbox属性，容易导致意外）
    * 注2、如果攻击者可以将潜在的恶意内容往用户的已沙箱化的 IFRAME 中显示，那么沙箱操作的安全性将不再可靠。推荐把这种内容放置到独立的专用域中，减小可能的损失。
    * 注3、sandbox属性在IE9及更早的版本中不被支持。
* src————被嵌入的页面的URL。对于空页面，应当使用"about:blank"以符合同源策略规范。
* srcdoc————该属性值可以是HTML代码，这些代码会被渲染到 IFRAME 中，如果同时指定了src属性，srcdoc会覆盖src所指向的页面（但如果浏览器不支持srcdoc属性，则src属性将生效）。该属性最好与sandbox属性同在。
* width————指定 IFRAME 元素的宽度（只支持像素单位）。
* 注意事项：
* 1、内联框架，像 FRAME 元素那样，会加入到window.frames这个伪数组中。
* 2、通过contentWindow属性，脚本可以访问 IFRAME 元素所包含的HTML页面的window对象。contentDocument属性则引用了iframe中的文档元素（等同于使用contentWindow.document），但IE8-不支持。
* 3、通过访问window.parent，脚本可以从框架中引用它的父框架的window。
* 4、脚本试图访问的框架内容必须遵守同源策略，并且无法访问非同源的window对象的几乎所有属性。同源策略同样适用于子窗体访问父窗体的window对象。跨域通信可以通过window.postMessage来实现。

# IMG
```
<!--以下例子中，当浏览器支持srcset属性时，图像的src属性将被忽略。因为srcset属性的值包含了宽度描述符('w')-->
<!--当媒体查询条件(max-width: 600px)命中时，图片将显示200px宽。其余情况下，图片将显示出视窗的一半的宽度-->
<img src="clock-demo-thumb-200.png" alt="Clock" srcset="clock-demo-thumb-200.png 200w,clock-demo-thumb-400.png 400w" sizes="(max-width: 600px) 200px, 50vw">
```
用于在文档中嵌入一张图片。
* alt————用于定义描述图片的替代文本。如果图片地址错误、图片格式不被支持、图片没有完全下载好，这些文本就会显示出来。如果图片本身不是关键内容（可省略的那种），则应当设置值为空字符串""，那样，在非可视化浏览器中在渲染的时候可能会忽略它。
* crossorigin—————这是一个HTML5新增属性。表明是否必须使用CORS完成相关图像的抓取。启用CORS的图像在 CANVAS 元素中可以重复使用而不会被污染。允许的值有：
    * 1、anonymous：执行一个跨域的请求（比如，请求头部带有 Origin: HTTP header）。但不发送证书（比如，没有 cookie，没有 X.509 证书，没有HTTP基本的授权认证）。如果服务器没有给源站证书（没有设置Access-Control-Allow-Origin: HTTP头），图像会被污染而且它的使用会被限制。
    * 2、use-credentials：一个有证书的跨域请求（比如，请求头部带有 Origin: HTTP header）被发送 （比如，有 cookie, 有 certificate, a有HTTP基本的授权认证）。如果服务器没有给源站发送证书（通过Access-Control-Allow-Credentials: HTTP header），图像将会被污染，且它的使用会受限制。
    * 3、不设置该属性：默认不使用CORS发起请求(例如，不会向服务器发送 HTTP 头部信息)，用以防止其在 CANVAS 中的使用。
* decoding————为浏览器提供一个解码的提示。可能只包括：
    * 1、sync：同步解码，在此期间，不渲染其他内容。
    * 2、async：异步解码，以减少其他内容的显示延迟。
    * 3、auto：默认值。由浏览器决定解码方式。
* height————指定 IMG 元素的高度（只支持像素单位）。
* ismap————指定该图片是否是服务器端map的一部分。如果是，那么每次点击的精确坐标将会被发送到服务器。（这个属性只会在当 IMG 元素属于一个带有有效的href属性的 A 标签的子元素时，才有效）
* longdesc————一个指向该图像的更详细描述的链接，是对 alt 文本的补充。（可能值包括一个URL或者一个元素ID）
* sizes————这是一个HTML5新增属性。只与srcset属性共同起作用。其值是一个表示图片资源大小的以逗号分隔的一个或多个字符串。每一个资源大小包括：
    * 1、媒体条件。最后一项一定是被忽略的。
    * 2、一个资源的尺寸值。
    * 注1、资源尺寸大小指定了图片将要展示的大小。当sizes属性的资源字符串用宽度描述符('w')来修饰时，用户代理（浏览器）会根据srcset属性提供的值从sizes值中选择一个合适的资源大小(来使用)。被选中的资源大小将会影响图片本身的尺寸（如果图片元素没有应用css样式的话，还会影响图片的显示尺寸）。当然，如果 IMG 标签没有设置srcset属性值，或者没包含有带宽度描述符('w')的值时，属性sizes是无效的。
* src————图片的URL。此属性的必需的。在支持srcset的浏览器中，src被当做拥有一个像素密度描述符1x的候选图像进行处理，除非这个像素密度描述符已经在srcset中定义了，或者除非srcset包含了宽度描述符('w')。
* srcset————值为一个用逗号隔开的字符列表，用于指定用户代理（浏览器）可能使用的图像资源的集合。每个字符串包含有：
    * 1、一张图像的URL。
    * 2、可选项。此项跟在空白处（空格或制表符）后面。此项可以是：一个宽度描述符或者一个正整数直接加'w'，可以用sizes属性中的给予的资源大小除以该宽度描述符得出像素密度；一个像素密度描述符（正浮点数后面直接加'x'）。
    * 注1、如果没有指定描述符，则资源会分配一个默认的描述符：1x。
    * 注2、在同一个srcset属性下面混用宽度描述符和像素密度描述符是不对的。另外，重复的描述符也是不对的。
    * 注3、用户代理（浏览器）会根据它的考虑来选择可用资源中的任意一个。这为用户提供了可选的余地，或者为浏览器提供了根据带宽条件优化图片显示的可能。
* width————指定 IMG 元素的宽度（只支持像素单位）。
* usemap————指定一个与图像地图(image map)关联的元素不完全URL（以'#'开头）。如果 IMG 标签是一个 A 标签或 BUTTON 标签的后代，那么你不能使用该属性。（URL通常指向那个地图元素的name属性或id属性）
* 注意事项：
* 1、IMG 标签支持的图像格式包括：jpeg、gif(包括动画gif)、png、apng、svg、bmp、bmp ico、png ico。
* 2、剔除css的影响的前提下，IMG 标签是一个可替换元素。它自身没有基线。因此如果需要图像的底部跟基线进行对齐，则要应用css样式的vertical-align: baseline;属性。
* 3、一个图像是否有固有的宽度和高度，取决于它的类型。以svg图片为例，如果其根元素 SVG 没有设置width和height属性，那其作为图片就没有固有的维度（宽度和高度）。
* 4、当加载或渲染一张图片时，有几种情况会触发 IMG 元素的onerror事件：src属性没有设置或者设置为null；src属性值等于当前网页的URL；某些因素导致了图片的加载中止；图片的元数据加载被中止而导致图片没办法获取它的维度（宽度和高度），而且 IMG 元素的属性中也没设置相应的维度；用户代理（浏览器）压根不支持URL所指图片的格式。

# INPUT
```
<label for="textInput">Note the red caret:</label>
<input id="textInput" class="custom" size="32"/>
```
用于创建基于web表单的交互控件，以接收用户输入的数据。
* 该元素可以创建的控件类型(type)包括但不限于以下几种。
* 1、button：一个不带默认行为的按钮。
* 2、checkbox：一个用于指定选中或非选中的单值的复选框。
* 3、color：一个用于指定一种颜色的控件。(HTML5)
* 4、date：一个用于输入日期的控件（包括了年、月和日，但不包括时间）。(HTML5)
* 5、datetime-local：一个用于输入不含时区的日期和时间的控件。(HTML5)
* 6、email：一个用于编辑一个邮件地址的控件。(HTML5)
* 7、file：一个用于提供用户选择本地文件的控件（另设置accept属性来定义控件可以选择的文件类型，默认为"*"，即全部可选）。
* 8、hidden：一个不会显示出来的控件。但它的值可以被提交到服务器。
* 9、image：一个图像提交按钮（你必须使用src属性来定义图像的源以及使用alt属性来定义一份替代文本。也可以用height和width属性来定义图片的像素大小）。
* 10、month：一个用于输入不带时区的年月的控件。(HTML5)
* 11、number：一个只能输入数字的控件。(HTML5)
* 12、password：个值被遮盖的单行文本字段。可使用maxlength属性来指定输入的值的最大长度。（任何涉及到敏感信息如密码的表单都应当使用HTTPS协议，否则，浏览器会通过各种机制提示警告信息）
* 13、radio：一个用于指定选或不选的单选框（多个name属性相同的单选框，只能选中一个，并且选中了就不能更改为完全不选）。
* 14、range：一个用于输入在给定的范围内的数值控件（对数值的准确度要求不高的情况下使用，如音量调控）。(HTML5)
* 15、reset：一个用于将所关联的表单的内容重置为默认值的按钮。
* 16、search：一个用于输入搜索字符串的单行文本字段的输入框。换行会被从输入的值中自动移除。(HTML5)
* 17、submit：一个用于提交表单的按钮。
* 18、tel：一个用于输入电话号码的控件。换行会被自动从输入的值中移除，但不会执行其他语法。可以使用属性如pattern和maxlength来约束控件输入的值。恰当的时候，可以应用:valid和:invalid这两CSS伪类。(HTML5)
* 19、text：一个单行文本框。换行会被自动从输入的值中移除。
* 20、time：一个用于输入不带时区的时间值的控件。(HTML5)
* 21、url：一个用于输入一个URL地址的框。(HTML5)
* 22、week：一个用于输入年-周的日期控件。其值不带时区。(HTML5)
* 属性的解析则如下：
* type————控件渲染成的类型（参考上面所述的控件类型）。
* accept————当type属性值为"file"，该属性才能起作用，否则直接被忽略。该属性用于指定服务器会接收的文件(内容)类型。多个值时，用逗号进行分隔。不允许重复值。可接受的值包括：
    * 1、以 STOP 字符 (U+002E) 开始的文件扩展名。（例如：".jpg,.png,.doc"）
    * 2、一个有效的 MIME 类型，但没有扩展名。
    * 3、audio/* 表示音频文件。(HTML5)
    * 4、video/* 表示视频文件。(HTML5)
    * 5、image/* 表示图片文件。(HTML5)
* accesskey————已经升级为全局属性。
* autocomplete————这是一个HTML5新增属性。用于指定控件的值能否被浏览器自动补全。可接受的值包括：
    * 1、off：关闭自动补全（用户自己必须准确输入一个值，除非文档本身提供了自动补全方法）。
    * 2、on：打开自动补全（浏览器会根据用户以前使用输入控件时输入的值进行自动补全，但不限制值的种类）。
    * 3、name：完整的姓名。
    * 4、honorific-prefix：尊称的前缀（如"Mr."，"Ms."，"Dr."，"Mlle"）。
    * 5、given-name：名（名字第一部分）。
    * 6、additional-ame：中间名。
    * 7、family-name：姓（名字最后部分）。
    * 8、honorific-suffix：尊称的后缀（如"Jr."，"B.Sc."，"MBASW"，"II"）。
    * 9、nickname：昵称。
    * 10、email：邮件地址。
    * 11、username：用户名。
    * 12、new-password：一个新的密码（例如在创建一个账号或改变密码时记录下来的密码）。
    * 13、current-password：当前密码。
    * 14、organization-title：职位名称（如"Software Engineer"、"Senior Vice President"、"Deputy Managing Director"）。
    * 15、organization：组织名称。
    * 16、street-address：街道地址。
    * 17、address-line1、address-line2、address-line3、address-level4、address-level3、address-level2、address-level1：街道纵横名称。
    * 18、country：国家。
    * 19、country-name：国家名称。
    * 20、postal-code：邮政编码。
    * 21、cc-name、cc-given-name、cc-additional-name、cc-family-name、cc-number、cc-exp、cc-exp-month、cc-exp-year、cc-csc、cc-type：与支付相关的名称（例如 Visa 信用卡的相关信息）。
    * 22、transaction-currency：交易货币。
    * 23、transaction-amount：交易金额。
    * 24、language：偏好的语言（人的语言）。
    * 25、bday：生日。
    * 26、bday-day、bday-month、bday-year：生日的日、月、年。
    * 27、sex：性别标识（例如"Fa'afafine"）。自由式文本，不包括新行。
    * 28、tel：电话号码的完整形式，包括国家编码。（其他关于电话号码的信息有————tel-country-code、tel-national、tel-area-code、tel-local、tel-local-prefix、tel-local-suffix、tel-extension）
    * 29、url：公司、个人、与当前域相关的其他域的地址或联系方式的相关的主页或其他网页（其实就一统一资源标志符）。
    * 30、photo：公司、个人、与当前域相关的其他域的地址或联系方式的相关的图片、图标。
    * 注1：当 INPUT 元素没有指定autocomplete属性时，浏览器会使用 INPUT 元素所属的 FORM 元素的autocomplete属性。
    * 注2：在FireFox浏览器中，一个 INPUT 元素被设置为disabled后，刷新页面也会保持disabled状态。可设置autocomplete属性为"off"来解决。
    * 注3：对于现代浏览器，无论autocomplete属性设置了什么值，都不能阻止浏览器询问用户是否保存登录数据(用户名和密码)，如果用户选择了同意，当其再次访问该页面时，浏览器自动将这些登录数据填充到相应的 INPUT 元素中。
* autofocus————用于指定页面刚加载完成时，某个表单控件是否应当拥有输入焦点（除非用户改变了输入焦点，例如在别的控件中打字）。一个表单只能有一个控件拥有autofocus属性。如果一个控件被隐藏了，那么它的autofocus属性失效。控件的获取焦点会在控件加载完成前发生。
* capture————当 INPUT 元素的type属性被设置为"file"时，该属性将会指定直接从设备环境中捕获accept指定的类型的媒体。例如下面的例子：
    1、调用所在设备的照相机（user facing mode）：
```
    <input type="file" accept="image/*" capture="user">
```

    2、调用所在设备的摄像机（environment facing mode）：
```
    <input type="file" accept="video/*" capture="environment">
```

    3、调用所在设备的麦克风（default facing mode）：
```
    <input type="file" accept="audio/*" capture>
```

* checked————当 INPUT 元素的type属性被设置为"radio"或"checkbox"时，该属性将指定本控件是否被默认选中。当选择动作发生后，该属性会被忽略。在FireFox浏览器中，INPUT 元素被设置为checked后，刷新页面会保持checked状态。可设置autocomplete属性为"off"来解决。
* disabled————用于指定表单控件是否可用于交互。特别的是，在禁用了的控件中，点击事件将不被分发。同样，一个禁用了的控件的值不会与表单中其他控件的值一起被提交。（对于FireFox中的一个bug，可参照autocomplete属性中的注2）
* form————用于指定 INPUT 元素所关联的 FORM 元素。该属性的值必须是当前文档的一个 FORM 元素的id属性值。如果不指定form属性，该 INPUT 元素必须是一个 FORM 元素的后代。该属性的使用目的就是为了使 INPUT 元素可放置于文档的任意位置而不必成为 FORM 元素的子元* 素。当然，一个 INPUT 元素只能关联一个 FORM 元素。(HTML5)
* formaction————若 INPUT 元素是一个提交按钮或提交图片，表示处理该 INPUT 元素的信息的程序的URI。此属性将重写 INPUT 所在表单的action属性。(HTML5)
* formenctype————若 INPUT 元素是一个提交按钮或提交图片，表示表单提交时该 INPUT 元素所使用的文本格式。常用值有："application/x-www-form-urlencoded"(默认值)、"multipart/form-data"(提交的内容含文件类型时使用)、"text/plain"。此属性将重写 INPUT 所在表单拥有者的enctype属性。(HTML5)
* formmethod————若 INPUT 元素是一个提交按钮或提交图片，表示所属表单提交时所使用的HTTP方法。常用值有："post"、"get"。此属性将重写 INPUT 所在表单的method属性。(HTML5)
* formnovalidate—————若 INPUT 元素是一个提交按钮或提交图片，表示所属表单提交时不进行验证。此属性将重写 INPUT 所在表单的novalidate属性。(HTML5)
* formtarget————若 INPUT 元素是一个提交按钮或提交图片，表示所属表单提交时在何处显示返回结果。常用值有："_self"、"_blank"、"_parent"、"_top"。此属性将重写 INPUT 所在表单的target属性。(HTML5)
* height————若 INPUT 元素的type属性的值为"image"，该属性将为按钮定义所要展示图片的高度。(HTML5)
* list————指定一个为用户预定义的建议选项（即定义筛选选项）。值必须是当前文档中一个 DATALIST 元素的id属性值。当type属性的值为"hidden"、"checkbox"、"radio"、"file"或一个按钮类型（如 "reset"、"submit"）时，该属性将被忽略。(HTML5)
* max————该项（值 INPUT 元素）的(数字或日期时间)最大值。该属性的值不能设置为小于min属性指定的值。(HTML5)
* maxlength————若type属性的值为"text"、"email"、"search"、"password"、"tel"、"url"，该属性将指定用户可输入的字符（编码为UTF-16）的最大个数。对于其他控件类型，该属性将被忽略。该值可以超出size属性指定的值。不指定或指定为负值时，用户可以在输入框中输入无限的字符。另外，本属性的约束规则，仅在元素的value属性发生变化时才会执行。
* min————该项（值 INPUT 元素）的(数字或日期时间)最小值。该属性的值不能设置为大于max属性指定的值。(HTML5)
* minlength————若type属性的值为"text"、"email"、"search"、"password"、"tel"、"url"，该属性将指定用户可输入的字符（编码为Unicode编码）的最大个数。对于其他控件类型，该属性将被忽略。(HTML5)
* multiple————若type属性的值为"email"、"file"时，可以指定用户是否能输入多个值或选择多个文件。(HTML5)
* name————控件的名称。会（作为键值对的键）随着表单数据一起提交到服务器。
* pattern————若type属性的值为"text"、"email"、"search"、"password"、"tel"、"url"，该属性将指定一个检查(用户输入的)值的正则表达式。为了提升对用户友好度，在使用该属性时，应使用title属性来提示关于本正则表达式的描述。该正则表达式不能被正斜杠包着。(HTML5)
* placeholder————一个在控件中告诉用户应当输入什么内容的提示。该属性值绝对不能包含回车换行。(HTML5)
    * 注1：placeholder属性是不能替代 LABEL 元素的作用的，它们的使用目标不一样。LABEL 元素用于描述表单元素的角色，而placeholder属性则用于提示内容应当输入的格式。
    * 注2：placeholder属性在很多情况下会不显示，所以必须保证表单在没有placeholder的情况下也能被使用者所理解。
* readonly————用于指定控件的值能否被使用者修改。该属性的值无关重要。如果你需要对 INPUT 元素的值进行读写访问，千万别添加"readonly"属性。若type属性的值为"hidden"、"range"、"color"、"checkbox"、"radio"、"file"或一个按钮类型（如 "reset"、"submit"）时，该属性将被忽略。(HTML5)
* required————使用该属性表示提交一个表单前，用户必须为 INPUT 元素填充一个值。当type属性的值为"hidden"、"image"或一个按钮类型（如 "reset"、"submit"）时，该属性不能被使用。相应地，:optional和:required这俩css伪类将被应用到该字段。
* selectionDirection————用户选择输入框的文本时的方向。若用户通过鼠标从左往右选择输入框内的内容，属性值会变成"forward"；若用户从右往左选择输入框内的内容，属性值则变成"backward"。不同的平台下，该属性的值可能是不确定的，这时，值为"none"。例如在macOS中，默认的方向就是"none"，当用户开始通过键盘修改文本的选中时，该属性的值就会相应的变化。(HTML5)
* selectionEnd————用户选中的文本的最后一个字符的偏移位置。如果没有选中文本，则该属性值会指定输入光标后的一个字符在当前文本中的偏移位置。（简单说，就是要输入的下一个字符会占据的偏移位置）
* selectionStart————用户选中的文本的第一个字符的偏移位置。如果没有选中文本，则该属性值会指定输入光标后的一个字符在当前文本中的偏移位置。（简单说，就是要输入的下一个字符会占据的偏移位置）
* size————控件的初始化大小。如果type属性的值不为"text"或"password"（这种情况下，size指定了字符的整数数量），则该属性值会指定控件的像素大小。从HTML5开始，该属性只在当type属性为"text"、"email"、"search"、"password"、"tel"、"url"时有效，其他情况则会被忽略。另外，size属性的值必须大于0（默认值为20）。由于一种字体的不同字符会有有不同的字符宽度，因此，在字符数量跟size的值一致时，有些浏览器也不能保证 INPUT 元素内的所有这些字符都可以被看见。
* spellcheck————该属性值设置为"true"时，表示 INPUT 元素需要进行拼写和语法检查。值为"default"时，指定元素根据默认的情况选择相应的检查行为（可能基于父级元素的spellcheck属性值）。值为"false"时，指定元素不应当进行检查。(HTML5)
* src————当type属性的值为"image"时，该属性值将指定一张在图形化提交按钮上显示的图片的URI。其他情况下，该属性将被忽略。
* step————一个可以结合min和max属性来限制用户对数值和日期值进行设置的属性。值可以被设置为字符串"any"或者一个正浮点数。如果step属性没有被设置为"any"，则控件只接受最小值或最小值加上step属性值的倍数的所得值（除非有默认值）。step属性的可能值包括：(HTML5)
    * 1、属性type值为"datetime"，则step的单位为(秒)，默认step为"60"。（不要再使用"datetime"，新版HTML规范已去除该type类型，应当用"datetime-local"代替）
    * 2、属性type值为"date"，则step的单位为(日)，默认step为"1"。
    * 3、属性type值为"month"，则step的单位为(月)，默认step为"1"。
    * 4、属性type值为"week"，则step的单位为(周)，默认step为"1"。
    * 5、属性type值为"time"，则step的单位为(秒)，默认step为"60"。
    * 6、属性type值为"datetime-local"，则step的单位为(秒)，默认step为"60"。
    * 7、属性type值为"number"，则step的单位为(1)，默认step为"1"。
    * 8、属性type值为"range"，则step的单位为(1)，默认step为"1"。
* tabindex————已升级为全局属性。
* value————控件的初始值。该属性是可选属性。
    * 注1、在type为"radio"或"checkbox"时，该属性的值用于指定某项被选中，在提交表单时，name属性的值会与value属性的值一起组成键值对。
```
        <!--情况1：radio带value属性-->
        <input type="radio" id="contactChoice1" name="contact" value="email"><!--如果该被选中，则提交表单时会产生键值对：[contact: email]-->
        <!--情况2：radio不带value属性-->
        <input type="radio" id="contactChoice2" name="contact"><!--如果该被选中，则提交表单时会产生键值对：[contact: on]-->
```
    * 因此，相同name的radio有多项时，务必分别为每项设置value属性。
    * 注2、在重新加载页面前，如果value属性值发生了改变，那么刷新页面后，Gecko和IE类型浏览器会忽略HTML代码上的那个value属性指定的值。
* webkitdirectory————非标准属性（但浏览器支持良好，所有浏览器都支持）。当type属性的值为"file"时，用于指定是否只让用户选择目录。这能赋予脚步在该目录的操作权限：
```
    <input id="dialog" type="file" webkitdirectory />
    <script>
        window.onload = function(){
            var dialog = document.getElementById("dialog");
            dialog.onchange = function(e) {
                var files = this.files;
                var table = {};
                for (var i = 0; i < files.length; i++) {
                    var f = files[i];
                    var dt = new Date(f.lastModified);
                    table[i] = {
                        path: f.webkitRelativePath,
                        size: f.size,
                        modified: dt.toLocaleString();
                    };
                }
                console.table(table);   // 在控制台中打印该目录的所有文件的信息
            };
        }
    </script>
```
* width————若 INPUT 元素的type属性的值为"image"，该属性将为按钮定义所要展示图片的宽度。(HTML5)
* 注意事项：
* 1、从Gecko 2.0开始，一个type属性值为"file"的 INPUT 元素必须通过调用click()方法来打开文件选择器并让用户选择相应的文件。
* 2、无法通过脚步方式来对设置一个文件选择器的值（value）。
* 3、由于安全原因，文件 INPUT 元素的value属性的值不能获取源文件的真实路径（绝对路径）。通常只能拿到文件名。但通过webkitdirectory属性指定只能选择文件夹，则可以获取从所选的文件夹开始的相对路径。
* 4、关于更多不同type的 INPUT 元素的细节，请到 https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input 中选择相应的章节查看。

# INS
```
<ins>This text has been inserted</ins>
```
用于表示一些被添加(插入)到一个文档的文本。与 DEL 元素相对。
* cite————用于指定这些变化（为何需要插入这些文本）的解释资料的URI。例如一个会议纪要的链接(a link to meeting minutes)或者一个故障诊断系统的客服(a ticket in a troubleshooting sytem)。
* datetime————用于指定变化的日期和时间。值必须是一个有效的日期（时间是可选的）字符串。如果值不能被解析为一个可附带时间的日期的字符串，那么 INS 元素不会拥有一个管理的时间戳。

# KBD
```
<!--单独使用-->
<p>使用命令 <kbd>help mycommand</kbd> 查看"mycommand"命令的文档。</p>
<!--对应串联场景(1)-->
<p>你也可以用快捷键 <kbd><kbd>Ctrl</kbd>+<kbd>N</kbd></kbd> 创建一个新的文档。</p>
<!--对应串联场景(2)-->
<p>If a syntax error occurs, the tool will output the initial command you typed for your review:</p>
<blockquote>
    <samp><kbd>custom-git ad my-new-file.cpp</kbd></samp>
</blockquote>
<!--对应串联场景(3)-->
<p>To create a new file, choose the menu option <kbd><kbd><samp>File</samp></kbd>⇒<kbd><samp>New Document</samp></kbd></kbd>.</p>
<p>Don't forget to click the <kbd><samp>OK</samp></kbd> button to confirm once you've entered the name of the new file.</p>
```
HTML键盘输入元素(KeyBoarD)。用于提示用户应当或可以从一个键盘、语音设备或者任何其他文本输入设备输入指定的文本。该元素包含的文本默认以内联文本、浏览器的monospace字体（尽管这一点没有被HTML标准授权）为样式进行显示。
* KBD 元素可能被嵌套在 SAMP 元素（Sample Output）形成不同的组合，从而基于视觉线索表示各种输入形式或不同的输入内容。
* 这个元素只有全局属性。
* 注意事项：
* 1、其他元素可以与 KBD 元素串联着使用以表示更多的专门场景。当然，单独使用 KBD 元素也是有效的。
    * (1): 一个 KBD 元素嵌套在另外一个 KBD 元素中表示一个实际的键(键盘上的某个键)或者该输入机制下的某个单位输入。
    * (2)：在 SAMP 元素中嵌套一个 KBD 元素表示系统对用户输入回应的结果。
    * (3)：在 KBD 元素中嵌套一个 SAMP 元素表示用户接下来的输入应当基于系统的输出。例如菜单或者菜单项的名称、显示在屏幕上的按钮的名称。

# KEYGEN
被废弃了。勿用。

# LABEL
```
<label>Click me <input type="text"></label>
```
表示用户界面中一个项目的标题。
* for————指定在同一文档中的可标记的form相关元素的id。在文档中，第一个符合这样条件的控件（其id匹配 LABEL 元素的for属性的值）是被该 LABEL 元素所标记的控件。LABEL 元素也可以在拥有for属性的同时，包含这一个控件元素（只要for属性指向该控件元素即可）。
* 注意事项：
* 1、一个 LABEL 元素可以通过包含一个控件或者使用for属性来关联一个控件。一个 INPUT 元素则可以与多个 LABEL 元素进行关联。
* 2、LABEL 元素自身不会直接与表单进行关联。它们仅仅通过与它们关联的控件来间接关键表单。
* 3、当一个 LABEL 元素被点击或触碰时，若它关联了一个表单控件，则click事件也会出现在所关联的控件上。

# LEGEND
```
<!-- Form with fieldset, legend, and label -->
<form action="" method="post">
    <fieldset>
        <legend>Title</legend>
        <input type="radio" name="radio" id="radio">
        <label for="radio">Click me</label>
    </fieldset>
</form>
```
表示它的父级元素 FIELDSET 的内容的一个标题(caption)。
* 这个元素只有全局属性。

# LI
```
<ol>
    <li value="3">third item</li>
    <li>fourth item</li>
    <li>fifth item</li>
</ol>
```
常常用于代表一个列表中的一项。
* LI 元素必须被包含在一个有序列表(OL)、一个无序列表(UL)、一个菜单(MENU)中。在菜单和无序列表中，列表项常常用着重点（实心圆点）来展示。在有序列表中，它们则常常在左边带有一个升序的计算器，例如一个数字或字母。
* value————值为一个整数，用于指定在 OL 元素中的当前列表项的原始值。不管列表是以罗马数字或字母来展示，该属性允许的值只能是一个数字。从该项开始的列表项将以该整数为始点进行递增（如果后面的列表项不包含value属性的话）。该属性对 UL 或 MENU 元素的列表没意义。该属性在HTML4规范中被移除，但在HTML5规范中又被重新引入。另外，在Gecko 9.0之前的版本，负值会被不正确地转换为0，但从Gecko 9.0开始，所有整数值都能被正确地解析。

# LINK
```
<!--普通的使用方式-->
<link href="style.css" rel="stylesheet">
<!--带有title的使用方式，详见：https://developer.mozilla.org/en-US/docs/Web/CSS/Alternative_style_sheets -->
<link href="default.css" rel="stylesheet" title="Default Style">
<link href="fancy.css" rel="alternate stylesheet" title="Fancy">
<link href="basic.css" rel="alternate stylesheet" title="Basic">
<!--rel属性值为"preload"的使用方式-->
<link rel="preload" href="style.css" as="style">
<link rel="preload" href="main.js" as="script">
```
用于指定一个外部资源与当前文档之间的关系。该元素的使用方式包括了为导航定义一个相关框架。最常使用的方式则是链接到样式表。
* as————该属性只有当 LINK 元素的rel属性设置为"preload"时才起作用。它指定了 LINK 元素所加载的内容的类型，这对于内容优化、请求匹配、应用正确的内容安全策略、设置正确的Accept请求头是很有必要的。
* crossorigin————该可枚举属性指定了当取回相关资源时，是否必须使用CORS。允许CORS的图片可以被 CANVAS 元素复用而不被污染。可能的值包括了：
    * 1、"anonymous"：执行跨域请求（例如带有 Origin: 这个HTTP头部名），但不发送证书（例如，没有cookie，没有X.509证书，没有HTTP基础授权）。如果服务器不给源网站发送证书（通过不设置 Access-Control-Allow-Origin: 这个头部名），图片将被污染并且使用受限。
    * 2、"use-credentials"：执行跨域请求（例如带有 Origin: 这个HTTP头部名），并带有证书（例如，有cookie，有X.509证书，有HTTP基础授权）。如果服务器不给源网站发送证书（通过不设置 Access-Control-Allow-Origin: 这个头部名），图片将被污染并且使用受限。
    注1：如果没有指定该属性，那么请求资源时将不使用CORS（例如不带 Origin: 这个HTTP头部名），以阻止 CANVAS 元素对它的非污染使用。如果设置了一个无效值，那么它将被当做关键词"anonymous"使用。
* disabled————这是一个非标准属性（只有IE系列支持）。用于禁用一个链接关系。当与脚本共同使用时，该属性将可以被用来打开和关闭不同的样式表关系。
    * 注1：在HTML标准中并没有disabled属性，该disabled属性是在HTMLLinkElement这个DOM对象上。
    * 注2：将disabled作为一个HTML属性来使用是非标准的，只有一些浏览器在用。别用它了。如要实现类似的效果，可以通过 (1)压根不引入 LINK 元素；(2)通过在脚本中对StyleSheet这类DOM对象设置disabled属性。
* href————该属性用于指定一个被链接的资源的URL（可以是绝对的或相对的）。
* hreflang————指定被链接资源的语言（是人类的语言，不是编程语言）。值仅提供参考。只应当href属性出现时使用。
* media————指定被链接资源所应用到的媒介（如各种参数不一的屏幕、打印机等）。该属性值必须是一个媒体查询（如 @media screen,print ）。该属性主要用于链接到外部样式表时，准许用户代理（浏览器）采用最适合在当前设备运行的那个。
    * 注1：在HTML4中，该属性值只能是一个以空格分隔的简单的媒体描述列表（如 print、screen、aural、braille）。HTML5把它扩展到了可以应用任何种类的媒体查询，这是一个HTML4所允许值的超集。
    * 注2：不支持CSS3媒体查询的浏览器不会识别合适的链接。别忘了设置备用链接（在HTML4中所定义的媒体查询有限集合）。
* prefetch————这是一个非标准属性（只有Chrome和Opera支持）。用于指定该资源可能被下一个导航所所请求时，用户代理（浏览器）应当取回它。该属性会使得用户代理（浏览器）在未来的资源请求时响应得更快。
* rel————用于为被链接的文档与当前文本的关系进行赋名。该属性的值必须是一个以空格分隔的链接类型值（link types values）列表，具体值参考 https://developer.mozilla.org/en-US/docs/Web/HTML/Link_types 。该属性最常用于指定一个链接链接到一个外部的样式表，此时，rel属性被设置为"stylesheet"，href属性则被设置为一个外部样式表（用来样式化该页面）的URL。WebTV也支持在一个文档系列中，将属性rel设置为"next"来预加载下一页。
* sizes————为视觉媒体指定被包含在资源中的图标定义尺寸。该属性只能在当rel属性包含了"icon"时出现。可能值包括：
    * 1、"any"：意味着图标被当作向量格式，可以被缩放为任意大小。（如 image/svg+xml）
    * 2、一个以空格分隔的尺寸列表：格式为"[width in pixels]x[height in pixels]"或"[width in pixels]X[height in pixels]"。尺寸的每一个都必须被包含在资源中。
    * 注1：大部分图标格式只能存储一个单独的图标。因此大部分时间sizes属性只包含唯一一个入口(输入)。微软的ICO格式和苹果的ICNS格式就是这样。ICO的使用更加普遍，你应当使用它。
    * 注2：苹果的iOS系统不支持该属性，因此苹果的iPhone和iPad使用专门的、非标准的链接类型值（link types values）来定义图标通过网络剪片（Web Clip）或者开头占位符（start-up placeholder）的方式使用："apple-touch-icon"以及"apple-touch-startup-icon"。
* target————这是一个非标准属性（众多浏览器支持）。用于指定定义了链接关系（linking relationship）或将显示任何被链接资源的渲染的框架或窗口的名称（name）。
* title————该属性在 LINK 元素中有专门的语义。当该属性被用在一个设置了rel属性为"stylesheet"的 LINK 元素中时，它指定了一个偏好或替代样式表（a preferred or an alternate stylesheet）。对该属性的不当使用可能导致样式表别忽略。
* type————用于定义链接到的内容的类型。该属性的值应当是一个MIME类型（例如 text/html、text/css 等等）。该属性最常用于定义被链接的样式表的类型，即最常见的值为"text/css"（用来指定一个级联样式表格式）。它也被用在rel属性为"preload"链接类型中，以确保浏览器只下载它支持的文件类型。
* 注意事项：
* 1、一个 LINK 标签可以出现在 HEAD 元素中或者 BODY 元素中（或者两者都有）。位置这个事情取决于它是否有一个"body-ok"的链接类型（详情见：https://html.spec.whatwg.org/multipage/links.html#body-ok ）。如rel为"stylesheet"就是body-ok的，那么< link rel="stylesheet">就可以被放置在 BODY 标签中。
* 2、HTML 3.2版本中，只为 LINK 元素定义了 href、rel、rev（已废弃）、title 这几个属性。
* 3、HTML 2版本中，为 LINK 元素定义了 href、methods、rel、rev（已废弃）、title、urn 这几个属性。其中，methods和urn属性被后来的规则移除了。
* 4、HTML和XHTML规范都为 LINK 元素定义了事件句柄（event handlers），但没说清楚这些句柄应当如何使用。
* 5、XHTML 1.0版本以前，空元素如 LINK 要求带有一个末尾斜杠：< link /> 。

# MAIN
```
<!-- other content -->
<main role="main"><!-- role的作用是为了让旧版的 IE 浏览器也能识别 MAIN 元素 -->
    <h1>Apples</h1>
    <p>The apple is the pomaceous fruit of the apple tree.</p>
    <article>
        <h2>Red Delicious</h2>
        <p>These bright red apples are the most common found in many supermarkets.</p>
        <p>... </p>
    </article>
    <article>
        <h2>Granny Smith</h2>
        <p>These juicy, green apples make a great filling for apple pies.</p>
        <p>... </p>
    </article>
</main>
<!-- other content -->
```
用于表示一个文本的 BODY 标签中的主体内容、一个文档中的部分内容、一个应用。主体内容区由与中心主题直接相关的内容，或者中心主题扩展的内容，或者一个文档，或者一个应用的核心功能所组成。
* 在同一个页面中，可以使用多个 MAIN 元素。例如一个页面需要多个部分，每一个部分分别包含了特别的材料（如编辑框、广告等等），那么，为每个特别的部分包含一个 MAIN 元素来指出它们的主要内容，这是很有必要的。
* 这个元素只有全局属性。
* 注意事项：
* 1、一个 MAIN 元素中的内容在整个文档或包含它的部分中应当是独一无二的。
* 2、在一系列文档或者文档部分（如侧边栏、导航链接、版权信息、网站图标、搜索表单）中重复的内容不应当包含在 MAIN 元素中，除非它（如搜索表单）是所在页面的主要功能。
* 3、MAIN 元素对文档的大纲（outline）是没有贡献的。也就是说，不像 BODY 这样的元素，也不像 H2 这样的标题等等，MAIN 元素对页面结构的DOM概念是没有影响的。它就是个提供信息的。
* 4、关于 MAIN 元素，WHATWG规范和W3C规范有着巨大的差异：
    * (1)、WHATWG当前标准允许一个页面存在多个 MAIN 元素，但W3C规范只允许存在一个，除非其他的 MAIN 元素使用了hidden属性隐藏起来了。
    * (2)、WHATWG规范允许 MAIN 元素在任何文档流允许存在的地方使用。但是，W3C规范版本就不允许 MAIN 元素作为 ARTICLE、ASIDE、FOOTER、HEADER、NAV 等元素的后代元素。

# MAP
```
<map name="primary">
    <area shape="circle" coords="75,75,75" href="left.html">
    <area shape="circle" coords="275,75,75" href="right.html">
</map>
<img usemap="#primary" src="https://placehold.it/350x150" alt="350 x 150 pic">
```
与 AREA 元素共同使用以定义一个图片地图（image map），即一个可点击的链接区域。
* name————用于给地图（map）一个名称，这样它就能被关联了。该属性是必须出现的，而且必须有一个非空值（值也不能带有空格字符）。同一个文档中，同样的 MAP 元素中，该属性值不能(经过小写转换后)是同样的。如果id属性也存在，那么id和name的值必须是一模一样的。

# MARK
```
<!--MARK元素用于引用块中，表示文本对用户有特别的意义-->
<blockquote>
    It is a period of civil war. Rebel spaceships, striking from a hidden base, have won their first victory against the evil
    Galactic Empire. During the battle, <mark>Rebel spies managed to steal secret plans</mark> to the Empire’s ultimate weapon,
    the DEATH STAR, an armored space station with enough power to destroy an entire planet.
</blockquote>
<!--MARK元素用于其他地方，表示与用户活动相关的部分，例如搜索结果中匹配的关键词-->
<p>It is a dark time for the Rebellion. Although the Death Star has been destroyed, <mark class="match">Imperial</mark> troops have driven the Rebel forces from their hidden base and pursued them across the galaxy.</p>
<p>Evading the dreaded <mark class="match">Imperial</mark> Starfleet, a group of freedom fighters led by Luke Skywalker has established a new secret base on the remote ice world of Hoth.</p>
```
用于表示在围住的上下文中，由于相关性或重要性而被作记号或被高亮的文本，以示引用或标记。
* 这个元素只有全局属性。
* 注意事项：
* 1、当 MARK 元素用在一个引用（Q 元素）或块级引用（BLOCKQUOTE 元素）中时，它通常指定有特殊意义但原文却没标示出来的文本，又或者原作者不认为这些文本有特别的重要性却是需要读者去仔细识别的材料。就想象一下你在看书时，拿一支高亮笔标记你找到的感兴趣的内容好了。
* 2、在注意事项1之外，MARK 元素用于指定文档的内容中很可能与用户当前活动中相关的部分。例如指定一个搜索操作结果中匹配的词组。
* 3、如果只是为了使文本高亮，不要使用 MARK 元素，相反，应当使用 SPAN 元素加上css样式实现。
* 4、不要将 MARK 元素和 STRONG 元素搞混，MARK 元素用于指代有一定程度相关性的内容，而 STRONG 元素用于指定具有重要性的文本的跨度。

# MENU
废弃元素，不要使用。

# MENUITEM
废弃元素，不要使用。

# META
```
<meta charset="utf-8">
<!-- Redirect page after 3 seconds -->
<meta http-equiv="refresh" content="3;url=https://www.example.com">
```
用于表示不能被其他与元数据相关的元素（如 BASE、LINK、SCRIPT、STYLE、TITLE ）所表示的元数据。
* charset————用于声明一个页面的字符编码。值必须包含一个标准的字符编码的IANA MIME名称。鼓励使用"UTF-8"。
* content————用于包含：http-equiz属性或name属性的值的值。这取决于哪个被使用了。
* http-equiv————该属性用于包含一个HTTP头部的名称，因此被称为"http等价(警报)"。它可定义一个能改变服务器或用户代理（浏览器）行为的指令。指令的具体内容会放在content属性中，包括：
    * "content-security-policy"：允许程序员为当前页面定义一个内容策略。主要是帮维护人员指定所允许的服务器源以及脚步终端，以对抗跨站脚步攻击。
    * "refresh"：该指令能指定两点。一是当content属性只包含一个正整数时，页面会在这个秒数后重载。二是当content属性包含一个正整数加上";url="以及一个有效的URL地址时，页面会在这个秒数后重定向到该URL所指向的网页。
* name————该属性定义一块（段）文档级的元数据的名称。如果 META 标签上设置了 "itemprop"、"http-equiv"、"charset" 中的某一个，就不要再设置name属性了。该元数据名称所关联的值会包含在content属性中。name属性的可能值包括：
    * "application-name"：定义网页中在运行的应用的名称。它有可能被浏览器用来指定特定的应用。它跟 TITLE 元素常常只包含应用的名称不一样，它还包含一些像文档名称或一个状态等信息。（简单的网页不应当使用application-name）
    * "author"：文档作者的名字。
    * "description"：该网页内容的一个简短精确的摘要。FireFox以及Opera等浏览器会使用该项作为收藏书签页的默认描述。
    * "generator"：产生该网页的软件的识别码。
    * "keywords"：与网页内容相关的关键词。关键词之间用逗号分隔。
    * "referrer"：控制当前文档的请求中附加的 Referer HTTP 头部，这是一个实验性项。当几个冲突的策略同时被使用时，no-referrer策略将被应用。对应的content值可以为：
        * "no-referrer"、不发送 Referer HTTP 头部；
        * "origin"、发送当前文档的源；
        * "no-referrer-when-downgrade"、当请求的URL的安全等级与当前网页一致时（https -> https），将源作为一个referrer附加到请求头上。但是，如果请求的安全等级低于当前网页时（https -> http），则不发送。这是默认行为。
        * "origin-when-crossorigin"、对同源请求发送全URL（剥去了查询参数）。对于其他情况，则只发送源（协议 + Host + 端口）。
        * "unsafe-URL"、无论对同源还是跨源请求，都发送全URL（剥去了查询参数）。
    * 从这里开始则是一些比较少用到的项。
    * "creator"：指定文档创建者的名字，例如一个组织或一个机构。如果创建者多于一个，则应当使用多 META 标签来分别指明。
    * "googlebot"："robots"的一个同义词，只对谷歌的索引爬虫有用。
    * "publisher"：指定文档发布者的名字。
    * "robots"：指定协作型爬虫（机器人）在本页面的行为。对应的content值可以是一个以逗号分隔的列表：
        * "index"、允许机器人添加该页面的索引（默认行为）。被所有搜索引擎支持。
        * "noindex"、要求机器人别添加该页面的索引。被所有搜索引擎支持。
        * "follow"、允许机器人追踪页面上的跳转链接（默认行为）。被所有搜索引擎支持。
        * "nofollow"、要求机器人别追踪页面上的跳转链接。被所有搜索引擎支持。
        * "none"、与"noindex,nofollow"等同。只被 Google 支持。
        * "noodp"、如果有的话，阻止使用[打开目录对象]描述。因为页面描述将作为搜索引擎的收录描述。只被 Google、Yahoo、Bing 支持。
        * "noarchive"、要求搜索引擎别缓存页面内容。只被 Google、Yahoo、Bing 支持。
        * "nosnippet"、阻止搜索引擎结果显示页面的任何描述。只被 Google、Bing 支持。
        * "noimageindex"、如果作为一个索引图片的相关页面，要求该页面不显示。只被 Google 支持。
        * "nocache"、"noarchive"的同义词。只被 Bing 支持。
    * "slurp"："robots"的一个同义词。但只对 Yahoo 搜索爬虫引擎Slurp有效。
    * "viewport"：提示视窗最初范围的尺寸。只用在移动设备中。对应的content属性的值包括：
        * "width"、等号后边可以跟着一个正整数或者文本"device-width"。定义你想网站被渲染到视窗的像素宽度。
        * "height"、等号后边可以跟着一个正整数或者文本"device-height"。定义视窗的像素高度。还没有被任何浏览器使用过。
        * "initial-scale"、等号后边可以跟着"0.0"到"10.0"之间的一个整数。定义设备尺寸与视窗大小的比例。当设备处于纵向时，是"device-width"与viewport值的比例；当设置处于横向时，是"device-height"与viewport值的比例。
        * "maximum-scale"、等号后边可以跟着"0.0"到"10.0"之间的一个整数。可缩放的最大倍数。首先，该项必须大于或等于"minimum-scale"的值，否则该项将失效。浏览器可能忽略该设置（例如IOS10+系统会默认忽略该设置）。
        * "minimum-scale"、等号后边可以跟着"0.0"到"10.0"之间的一个整数。可缩放的最小倍数。首先，该项必须小于或等于"maximum-scale"的值，否则该项将失效。浏览器可能忽略该设置（例如IOS10+系统会默认忽略该设置）。
        * "user-scalable"、等号后边可以跟着"yes"或者"no"。如果设置为"no"，用户则不能在网页中进行缩放。默认值为"yes"。浏览器可能忽略该设置（例如IOS10+系统会默认忽略该设置）。
* 注意事项：
* 1、全局属性的name属性在 META 元素中有专门的意义。当一个 META 元素存在name、http-equiv或charset属性时，一定不能再为其设置itemprop属性。
* 2、不要使用不兼容ASCII的编码集，因为浏览器不认识这些编码时，有可能会将其解析为有害的内容（如将非HTML内容解析为HTML），这些编码包括："JIS_C6226-1983"、"JIS_X0212-1990"、"HZ-GB-2312"、"JOHAB"、"ISO-2022"家族、"EBCDIC"家族。
* 3、用于声明字符编码的 META 必须位于 HEAD 元素中，而且必须在 HTML 元素中的第一个1024字节中。因为有些浏览器只在这两个条件下选择一个字符编码。
* 4、声明字符编码的 META 元素只是决定一个页面字符编码的算法的一部分。请求响应头部字段Content-Type以及任何字符命令标签都会覆盖该元素的声明。
* 5、所声明的字符编码集必须匹配页面在编写保存时所应用的字符编码，以避免字符乱码以及安全漏洞。
* 6、强烈推荐定义字符编码集。如果一个页面的编码是未定义的，那么（被）跨脚步技术（所攻击）是有可能的。
* 7、一个声明了charset属性的 META 标签是等同于HTML5前的另一个标签的：< meta http-equiv="Content-Type" content="text/html;charset=IANAcharset">。IANAcharset指代charset的值。该标签依然可用，只是不推荐使用了。
* 8、别使用 META 标签设置为一个 XHTML 设置 MIME 类型。因为 META 元素不能改变 XHTML 文档或 HTML5 的XHTML序列化文档的文档类型。
* 9、依赖于所设置的属性，元数据的种类可以分为：
    * 一、如果设置了name属性，则其是文档级元数据，将被应用于整个网页；
    * 二、如果设置了http-equiv属性，则其是编译指令，通常是由网站服务器给出的指导网页如何服务的信息；
    * 三、如果设置了charset属性，则其是一个字符集声明，是网页使用的字符编码；
    * 四、如果设置了itemprop属性，则其是用户定义元数据，当元数据的语义是用户指定时，其对于用户代理（浏览器）而言其是透明的。

# METER
```
<p>Heat the oven to <meter low="150" high="300" min="200" max="500" value="350">350 degrees</meter>.</p>
```
用于表示一个已知范围中或一个片段值中的一个标量值（跟向量值相对）。
* value————当前的数字值。如果设置了最小值（min 属性）和最大值（max 属性），该值必须位于最小值和最大值之间，否则会自动调整到这个区间的端点。如果没指定或指定的值不符合要求，则值为"0"。
* min————值域的较低边界数值。如果元素指定了max的值，则必须小于最大值。默认值为"0"。
* max————值域的较高边界数值。如果元素指定了min的值，则必须大于最小值。默认值为"1"。
* low————用于表现数值相对较低的视觉效果。值必须大于min的值以及小于max、high的值。当value位于min与low所形成的区间时，元素 METER 会表现出当前数值相对较低的视觉效果（例如在Chrome中显示红色填充）。若不指定该属性，其值默认等于min的值。
* high————用于表现数值相对较高的视觉效果。值必须小于max的值以及大于min、low的值。当value位于high与max所形成的区间时，元素 METER 会表现出当前数值相对较高的视觉效果（例如在Chrome中显示绿色填充）。若不指定该属性，其值默认等于max的值。
* optimum————用来指示最优/最佳取值。它必须在正确的值域内（由最小值属性和最大值属性定义）。当使用了low和high属性时，它指明哪一个取值范围是更好的。例如，假设它介于最小值和low之间，那么lower区间就被认为是更佳的取值范围。
* form————用来将 METER 元素与一个 FORM 元素（与该 METER 元素相关）连结起来。例如，一个 METER 元素可能被用于展示一个type为number的 INPUT 元素的值的范围。如果该 METER 元素本身属于 FORM 元素的后代，则可省略该属性。

# NAV
```
<nav class="menu">
    <ul>
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Contact</a></li>
    </ul>
</nav>
```
用于展示网页中的导航链接部分（该导航链接可以是导向当前文档，奕可以导向其他网页）。通常的例子有 菜单、内容表格、索引等。
* 这个元素只有全局属性。
* 注意事项：
* 1、没必要为所有的链接都包裹上一层 NAV 标签。NAV 元素只应用于导航链接的主要块。典型的，FOOTER 元素就常常包含有链接列表，但它们并不需要包含于一个 NAV 元素中。
* 2、一个文档可能有多个 NAV 元素，例如一个用于网站导航，一个用于页面内导航。
* 3、用户代理，例如为残疾用户服务的屏幕播音器，可以根据该元素决定是否忽略仅有导航内容的初始解析。

# NOSCRIPT
```
<noscript>
    <!-- anchor linking to external file -->
    <a href="https://www.mozilla.com/">External Link</a>
</noscript>
<p>Rocks!</p>
```
用于定义插入到不支持脚本类型或暂时关闭脚本功能的 HTML 文档中的内容。当浏览器支持脚本执行时，NOSCRIPT 的内容不会出现在文档中；反之，NOSCRIPT 的内容便会添加到文档中并显示。
* 这个元素只有全局属性。

# OBJECT
```
<!-- Embed a flash movie -->
<object data="movie.swf" type="application/x-shockwave-flash"></object>
<!-- Embed a flash movie with parameters -->
<object data="movie.swf" type="application/x-shockwave-flash">
    <param name="foo" value="bar">
</object>
```
用于展示外部资源。只要资源能被当成 一个图片、一段嵌入式的浏览上下文或一份能被一个插件处理的内容 便可。
* data————外部资源的有效的URL地址。该元素中，data与type属性，必须至少有一个是被定义的。
* form————用于指定与该 OBJECT 元素相关联的 FORM 元素（即 OBJECT 所属于的 FORM 元素）。值为处于统一文档中的一个 FORM 元素的id属性的值。
* height————所展示的资源的高度，单位为像素。（只支持绝对值，不支持百分比）
* name————在HTML5中，值为有效的浏览上下文(外部资源)的名称；在HTML4中，值为控件的名称。
* type————根据data属性所指定的资源的内容类型。该元素中，data与type属性，必须至少有一个是被定义的。
* typemustmatch————布尔属性，用于指定type属性的值是否必须与资源的实际内容类型匹配。(HTML5)
* usemap————用于指定关联到一个 MAP 元素的哈希名称（hash-name）。值的结构为 一个"#"后面跟着一个 MAP 元素的name属性的值。
* width————所展示的资源的宽度，单位为像素。（只支持绝对值，不支持百分比）

# OL
```
<!--默认以阿拉伯数字作为序号类型，默认升序，默认开始值为 1-->
<ol>
    <li>first item</li>
    <li>second item</li>
    <li>third item</li>
</ol>
<!--以罗马数字作为序号类型，倒序，默认开始值为 5-->
<ol type="i" start="5" reversed>
    <li>foo</li>
    <li>bar</li>
    <li>spam</li>
</ol>
```
用于展示一个有序列表，通常渲染为一个带有序号的列表。
* reversed————布尔属性，用于指定列表是否以反序方式排列，通常来说，就是序号由大变小。(HTML5)
* start————起始的整数值，无论序号类型是阿拉伯数字、罗马数字还是字母，均以数字代表。例如，为了将字母"C"作为开始序号，设置start为"3"即可。另外，该属性在HTML4中曾被抛弃，但在HTML5中又被重新引入。
* type————用于指定数字类型
    * 'a'：序号类型为小写字母；
    * 'A'：序号类型为大写字母；
    * 'i'：序号类型为小写罗马数字；
    * 'I'：序号类型为大写罗马数字；
    * '1'：序号类型为阿拉伯数字（默认值）。
    * 注1：type所指定的类型集将应用于 OL 元素所包含的全部列表，除非内部的 LI 元素设置了自己的不同的type属性值。
    * 注2：该属性在HTML4中曾被抛弃，但在HTML5中又被重新引入。除非列表的序号数字是相关的（例如在法律文档与技术文档中，条目是跟它的序号数字/字母相关的），否则应当以CSS中的list-style-type属性替代该属性的使用。
* 注意事项：
* 1、通常，有序列表条目以排序数字前置的方式显示，适合阿拉伯数字、字母、罗马数字甚至简单的子弹符号等任何形式。该排序数字样式并没有定义在页面的HTML描述中，但它与CSS的list-style-type属性相关。
* 2、对于有序列表而言，是没有深度限制的。只按照能否实现来说的话，OL 和 UL 元素相互替代使用也是可以的。
* 3、OL 和 UL 都代表了一堆条目的列表。不同之处在于，对于 OL 元素而言，序号是有意义的。至于决定使用哪一个，可以这么考虑：尝试改变各项的顺序，如果整个列表的意思改变了，则应该使用 OL 标签，反之，使用 UL 是比较合适的。

# OPTGROUP
