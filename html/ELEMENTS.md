## 所有标签
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

## A
```html
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

## ABBR
```html
<abbr title="Internationalization">I18N</abbr>
```
用于向搜索引擎解析这是一个缩写词并通过title属性提供完整的描述。
* 这个元素只有全局属性。
* 注意事项：在默认样式方面，一般的浏览器就会跟 SPAN 一样。Opera、Firefox和其他一些浏览器给这个元素的内容添加一条点状下划线 。一些浏览器不仅添加点状下划线，而且还把元素的内容添加小写大写字母的样式。为了避免这个样式，在CSS中添加font-variant: none 。

## ACRONYM
```html
<acronym title="World Wide Web">WWW</acronym>
```
功能基本和 ABBR 一致。已过时，请使用 ABBR 代替。

## ADDRESS
```html
<address>
  <p>Chris Mills, Manchester, The Grim North, UK</p>
  If you see any bugs, please <a href="mailto:webmaster@somedomain.com">contact webmaster</a>
</address>
```
用于描述文章编写者或网站拥有者(组织)的联系信息。内容可包括物理地址，URL，email地址，电话号码，社交媒体链接，地理坐标等待。
* 这个元素只有全局属性。
* 注意事项：ADDRESS 不能与 ADDRESS 产生嵌套关系。

## AREA
```html
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

## ARTICLE
```html
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

## ASIDE
```html
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

## AUDIO
```html
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
* played————一个TimeRanges对象，表示所有已播放的音频片段。
* preload————可能的值有：
  * "none"：指定声音不应当自动加载。
  * "metadata"：指定只自动加载声音的元数据（例如声音长度信息）。
  * "auto"：自动加载整个声音文件。
  * ""：跟"auto"一样。
  * 注1：如果设置了autoplay属性，preload属性则无效。
* src————指定音频的URL（可选项）。你也可以通过在 AUDIO 标签块中嵌入一个 SOURCE 标签来指定声音源，从而替代src属性。
* volume————指定播放音量。范围是0.0(静音) - 1.0(最大音量)。
* 注意事项：
* 1、建议提供浏览器不支持音频播放时的替代内容。
* 2、时间偏移量目前是指定为float类型的值，表示偏移的秒数，但时间偏移量值的定义还没有完成，有可能会变更。
* 3、VIDEO 标签可以通过嵌入 TRACK 元素包含子标题和字幕，但 AUDIO 不可以。

## B
```html
<b class="text_bold">这是加粗字体</b>
```
一个单纯的样式标签，指定文本要用粗体（用于吸引读者的注意）。
* 这个元素只有全局属性。
* 注意事项：如果是为了突出内容的重要性，那么建议使用 STRONG 代替。如果只是单纯为了加粗字体，才使用该标签（最好加以class属性来同时设置font-weight为"bold"值，以防止下一版本废弃该标签）。

## BASE
```html
<base target="_blank" href="http://www.example.com/">
```
用于指定所在文档的所有相对URL路径的基本URL路径。
* 如果需要在JS代码中获取该路径，可以通过document.baseURI拿到。
* href————如果设置了该属性，那本元素必须放置在其他带有URL值的元素之前。该属性值允许绝对路径和相对路径。
* target————为没有使用target引用属性的元素指定一个名字或关键字，当元素的超链接或导致导航的形式被激活时，指定显示结果的默认位置（例如标签页，窗口或者内联框）。常用值包括：_self、_blank、_parent、_top。
* 注意事项：
* 1、一个文档只能拥有一个 BASE 元素（如果设置了多个，则只是第一个有效，其余的会被忽略）。
* 2、OpenGraph元标签不认识 BASE 标签，因此需要一直使用全路径。

## BDO
```html
<bdo dir="rtl">感谢您对HTML的支持</bdo>
```
用于解析dir属性，即修改文字的方向。
* dir————值有两个："ltr"，文字从左到右；"rtl"，文字从右到左。
* 注意事项：HTML4不支持对 BDO 标签添加事件监听器。

## BLOCKQUOTE
```html
<blockquote cite="http://developer.mozilla.org">
  <p>This is a quotation taken from the Mozilla Developer Center.</p>
</blockquote>
```
用于表示其中的文字是引用内容。若引文来源于网络，则可以将原内容的出处 URL 地址设置到 cite 特性上。
* 通常在渲染时，这部分的内容会有一定的缩进。可以使用CSS中的margin属性来改变 BLOCKQUOTE 的缩进。
* cite————指定一个标注引用的信息的来源文档或者相关信息的URL。通常用来描述能够解释引文的上下文或者引用的信息。
* 注意事项：如果想要使用短引用（行间引用），可以使用 Q 标签。若要以文本的形式告知读者引文的出处（引用出处）时，可以通过 CITE 元素。

## BODY
```html
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

## BR
```html
<br>
```
用于文本换行（相当于回车键）。
* 这个元素只有全局属性。
* 注意事项：如果只是单纯的为了增加文本段落之间的间隔，不要用 BR ，而应当用margin属性来实现。

## BUTTON
```html
<button type="submit" name="myButton" value="foo">Click me</button>
```
表示一个可点击的按钮。可用于表单或者其他需要按钮的地方。
* 默认情况下，按钮会呈现与用户主机相似的样式，基于user agent。
* autofocus————指定当页面初始化时按钮必须自动获得输入焦点（只有一个表单关联元素可以指定该属性）。(HTML5)
* disabled————当值为"true"时，用户不能与该按钮交互。若该属性没有设置，则从 FIELDSET 等包含元素中继承。默认值为"false"。
* form————指定本按钮所属的 FORM 标签（值就是 FORM 的id）。若不设置该属性，则按钮归属于父级的 FORM 元素。因此设置了该属性可以让 BUTTON 元素出现在页面的任何位置。(HTML5)
* formaction————表示程序处理 BUTTON 提交信息的URI。此属性将重写 BUTTON 所在表单的action属性。(HTML5)
* formenctype————若按钮是提交类型，则指定所属表单提交时所使用的文本格式。常用值有：
  * "application/x-www-form-urlencoded"(默认值)。
  * "multipart/form-data"(提交的内容含文件类型时使用)。
  * "text/plain"。
  * 注1：此属性将重写 BUTTON 表单拥有者的enctype属性。(HTML5)
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

## CANVAS
```html
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

## CAPTION
```html
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

## CITE
```html
<p>More information can be found in <cite>[ISO-0000]</cite>.</p>
```
用于描述一个被引用的作品的相关信息，必须包含有该作品的标题或URL。相关信息也可能是一个根据合适的上下文的相关引用元数据而约定的简写形式。
* 这个元素只有全局属性。
* 注意事项：
* 1、可以被引用的具有创造性的作品包括：一本书、一份研究论文、一篇文章、一首诗、一篇乐谱、一首歌、一份戏剧或电影剧本、一部电影、一集电视剧、一场游戏、一座雕像、一幅画、一则戏剧作品、一场话剧、一部歌剧、一张唱片、一场展览、一份法律案例报告、一份计算机程序、一个网站、一张网页、一次推文或评论、一次论坛推文或评论、一篇Twitter上的推文、一篇Facebook上的推文、一次书面或口头上的陈述 等等。
* 2、值得注意的是，W3C规范所说的与创造性的作品相关的信息，可能包括了作品的作者名称。但是，WHATWG规范的说法则相反：任何时候、任何情况下，CITE 都不应当包含一个人的名字。
* 3、应当在 BLOCKQUOTE 元素或 Q 元素上使用cite属性来标明所引用的材料。
* 4、CITE 元素的默认样式是font-style为italics。可以通过css设置font-style来重置该样式。

## CODE
```html
<p>
  The function 
  <code>selectAll()</code> 
  highlights all the text in the input field so the user can, for example, copy or delete the text.
</p>
```
呈现一段计算机代码。默认情况下，它以浏览器的默认等宽字体显示。
* 这个元素只有全局属性。
* 注意事项：css规则可以覆盖浏览器默认的 CODE 标签字体样式。但用户设置的浏览器字体选项可能会超过css的优先级，使之无效。

## COL
```html
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

## COLGROUP
```html
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

## CONTENT
已废弃，请用 SLOT 元素代替。html

## DATA
```html
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

## DATALIST
```html
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

## DD
```html
<dl>
  <dt>Firefox</dt>
  <dd>A free, open source, cross-platform, graphical web browser</dd>
  <!-- other terms and definitions -->
</dl>
```
用于指明一个描述列表 DL 元素中一个术语的描述。
* nowrap————"yes"表示描述文本不会被包裹。默认值为"no"。（此属性为非标准属性）
* 注意事项：该元素只能作为 DL 元素的子元素出现，并且必须跟着一个 DT 元素。

## DEL
```html
<p><del>This text has been deleted</del>, here is the rest of the paragraph.</p>
<del><p>This paragraph has been deleted.</p></del>
```
用于展示文档中被删除了的文本。（元素 INS 则恰好相反：用户标识文档中新增的文本）
* 在样式上，这个元素通常会被渲染上一根划过的线。
* cite————指定一个解释该变化的源头的URI。
* datetime————指定变化的日期以及时间。值必须是一个有效的日期时间字符串。

## DETAILS
```html
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

## DFN
```html
<p>
  <strong>HTML定义元素</strong>
  (
  <strong>
    <dfn id"definition-dfn">&lt;dfn&gt;</dfn>
  </strong>
  )用于指定一个定义语句或段落的被定义术语。
</p>
<p>
  你可以通过点击
  <code>
    <a href="#definition-dfn">&lt;dfn&gt;</a>
  </code>
  元素跳到相应词条的解析。
</p>
<p>
  <dfn>
    <abbr title="Hubble Space Telescope">HST</abbr>
  </dfn>
  是指美国宇航局发射的在轨超过了20年的太空探测科学装备。
</p><!--这是定义也语句-->
<p>
  <abbr title="Hubble Space Telescope">HST</abbr>
  比之前发射的其他深空探测装备先进很多。
</p><!--这不是定义也语句-->
```
用于指定一个定义语句或段落的被定义术语。 DFN 元素的最近祖先标签包括了 P 标签、DT/DD 标签对、SECTION 标签，这些标签用于包裹对 DFN 含有的被定义术语的解析。
* 从功能上说，该标签没有太大的作用。（主要目的就是为了使文档更符合语义化）
* title————该属性比较特殊：当该标签内是一个缩列词时，值可以是缩列词的完整形式，因此值就是被定义术语；当标签内的词有一个单独的子元素 ABBR 时(连其他文本也没有)，ABBR 上的title属性值就是被定义术语；否则，DFN 标签上的文本就是被定义术语。若 DFN 包含了本属性，则 DFN 必须只含有被定义的术语，而不能其他文本。
* 注意事项：
* 1、如果 DFN 上有id属性，那么你可以通过 A 标签来连接该 DFN 元素。这样的连接可以用于帮助读者快速导航到术语的定义之处（为 A 标签指定href="#id"，使其能跳转到 DNF 标签的位置）。
* 2、被定义术语的具体值需根据title属性及其标签包含的内容决定：DFN 标签有title属性，那么被定义术语就是该title属性的值；若 DFN 标签包含有 ABBR 元素且 ABBR 元素含有title属性，则被定义术语是 ABBR 元素上的title属性的值；否则，被定义术语就 DFN 包含的文本。

## DIALOG
```html
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

## DIV
```html
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

## DL
```html
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

## DT
```html
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

## EM
```html
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

## EMBED
```html
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

## FIELDSET
```html
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

## FIGCAPTION
```html
<figure>
  <figcaption><cite>Edsger Dijkstra :-</cite></figcaption>
  <p>"If debugging is the process of removing software bugs,<br />then programming must be the process of putting them in"</p>
</figure>
```
用于标记一句与一副图像或一则说明(插画)（图像、插画、说明通常跟随在 FIGCAPTION 标签后面）相关的说明/标题，FIGURE 标签就是 FIGCAPTION 标签的直接父元素。
* 这意味着 FIGCAPTION 标签在 FIGURE 块里是第一个或最后一个子元素。同时 FIGCAPTION 元素是可选的；如果没有该元素，这个父节点的图片只是会没有说明/标题。
* 这个元素只有全局属性。

## FIGURE
```html
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

## FOOTER
```html
<footer>
  Some copyright info or perhaps some author info for an &lt;article&gt;?
</footer>
```
用于表示离本元素最近的分片内容或分片内容的根的页脚。本标签通常包含所在分片的作者、版权数据或文档的相关链接。
* 这个元素只有全局属性。
* 注意事项：
* 1、FOOTER 元素中的有关于作者的信息应当包含在 ADDRESS 标签中。
* 2、FOOTER 元素并不属于分片内容，因此不会为文档纲要引入一个新的章节。

## FORM
```html
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
* autocomplete————这是一个HTML5新增属性。指定输入框元素是否默认被浏览器自动完成值的填写（当然，这个设定会被输入框或文本域本身的autocomplete属性值所覆盖）。可能的值有：
  * "off"：指定用户在每次使用输入框时，都必须明确地输入值，又或者文档本身提供自己的自动完成方法（浏览器是不会自动完成输入的）。
  * "on"：浏览器会根据用户以前在改输入框中输入的内容，自动将其输入填充到输入框中。。
* enctype————当method属性被设置成"post"时，enctype就是用于指定要提交到服务器的表单的内容的MIME类型。常用值有：
  * "application/x-www-form-urlencoded"(默认值)。
  * "multipart/form-data"(提交的内容含文件类型时使用)。
  * "text/plain"。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formenctype属性覆盖。
* method————浏览器提交表单的HTTP方法。常用值有：
  * "post"(对应HTTP的"POST"方法。表单数据将被包含在表单体中，然后发送给服务器)、
  * "get"(对应HTTP的"GET"方法。表单数据将附在要请求URI的查询位置中，即"?"后面，然后发送给服务器。这种方式要求表单没有副作用，并且数据需要进行URI编码)。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formenctype属性覆盖。
* name————表单的名称(name)。
* novalidate————指定表单在提交时是否不要做验证。不指定该属性的情况下，表单是会被验证的。默认的设置可以被 BUTTON 和 INPUT 元素设置的formnovalidate属性覆盖。(html5)
* target————值为一个名称或关键词，用来指定在何处显示提交表单后收到的返回信息。常用值有："_self"、"_blank"、"_parent"、"_top", 标签 IFRAME 的name属性值。该属性的值可能会被 BUTTON 和 INPUT 元素设置的formtarget属性覆盖。
* 注意事项：
* 1、对于大多数浏览器来说，设置autocomplete属性并不会阻止浏览器询问用户是否想保存密码(包括用户名和密码)到本地的行为。如果用户同意了浏览器的存储密码的询问，则浏览器会在用户下次访问该网页时自动填充登录所需要的信息。
* 2、如果是由于文档本身提供了自己的自动完成方法而使你设置 FORM 元素的autocomplete属性为"off"，那么你也应当为表单中的每一个输入框设置autocomplete属性为"off"。
* 3、对于谷歌的Chrome浏览器来说，如果只在表单设置了autocomplete为"off"，但输入框没设置，则浏览器会提示说"该表单禁用了自动完成功能"。因此，最好对每个输入框都设置自定义的autocomplete属性，以增强用户体验。

## H1
## H2
## H3
## H4
## H5
## H6
```html
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

## HEAD
```html
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

## HEADER
```html
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
  <p>
    <a href="https://janesmith.com/the-planet-earth/">
      Continue reading....
    </a>
  </p>
</article>
```
用于展示介绍性的内容，通常是一组介绍性或导航性的帮助。
* 该元素可能包含一些标题元素，也可能包括其他的例如一个图标、一个搜索表单、一个作者的姓名等等。
* 这个元素只有全局属性。
* 注意事项：
1、HEADER 元素不属于分片内容，因此不会为文档纲要引入一个新的章节。（也就是说，一个 HEADER 元素常常会被用来包含周围章节的标题(H1-H6元素)，但这并不是必须的）

## HR
```html
<p>This is the first paragraph of text.</p>
<hr>
<p>This is the second paragraph of text.</p>
```
用于在段落层级元素之间显示主题性的隔离。（例如一个故事的场景变换、一个话题的主题改变）
* 历史上，这个元素会生成一根水平线（现在可能也会）。但这个元素由于被赋予了语义化功能，所以，如果你仅仅是希望画一根水平线，可以考虑用css样式来实现。
* 这个元素只有全局属性。

## HTML
```html
<!DOCTYPE html>
<html>
  <head>...</head>
  <body>...</body>
</html>
```
用于表示一个HTML文档的根(最高层级元素)。所有其他元素都必须是 HTML 元素的后代。
* xmlns————指定文档的XML命名空间，默认值是 "http://www.w3.org/1999/xhtml" 。在XML解析器中，这个属性是必须的；在TEXT/HTML文档中，这个则是可选的。

## I
```html
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

## IFRAME
```html
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

## IMG
```html
<!--以下例子中，当浏览器支持srcset属性时，图像的src属性将被忽略。因为srcset属性的值包含了宽度描述符('w')-->
<!--当媒体查询条件(max-width: 600px)命中时，图片将显示200px宽。其余情况下，图片将显示出视窗的一半的宽度-->
<img src="clock-demo-thumb-200.png" alt="Clock" srcset="clock-demo-thumb-200.png 200w,clock-demo-thumb-400.png 400w" sizes="(max-width: 600px) 200px, 50vw">
```
用于在文档中嵌入一张图片。
* alt————用于定义描述图片的替代文本。如果图片地址错误、图片格式不被支持、图片没有完全下载好，这些文本就会显示出来。如果图片本身不是关键内容（可省略的那种），则应当设置值为空字符串""，那样，在非可视化浏览器中在渲染的时候可能会忽略它。
* crossorigin—————这是一个HTML5新增属性。表明是否必须使用CORS完成相关图像的抓取。启用CORS的图像在 CANVAS 元素中可以重复使用而不会被污染。允许的值有：
  * 1、anonymous：执行一个跨域的请求（比如，请求头部带有 Origin: HTTP header）。但不发送证书（比如，没有 cookie，没有 X.509 证书，没有HTTP基本的授权认证）。如果服务器没有给源站证书（没有设置Access-Control-Allow-Origin: HTTP头），图像会被污染而且它的使用会被限制。
  * 2、use-credentials：一个有证书的跨域请求（比如，请求头部带有 Origin: HTTP header）被发送 （比如，有 cookie, 有 certificate, 有HTTP基本的授权认证）。如果服务器没有给源站发送证书（通过Access-Control-Allow-Credentials: HTTP header），图像将会被污染，且它的使用会受限制。
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

## INPUT
```html
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
```html
  <input type="file" accept="image/*" capture="user">
```

  2、调用所在设备的摄像机（environment facing mode）：
```html
  <input type="file" accept="video/*" capture="environment">
```

  3、调用所在设备的麦克风（default facing mode）：
```html
  <input type="file" accept="audio/*" capture>
```

* checked————当 INPUT 元素的type属性被设置为"radio"或"checkbox"时，该属性将指定本控件是否被默认选中。当选择动作发生后，该属性会被忽略。在FireFox浏览器中，INPUT 元素被设置为checked后，刷新页面会保持checked状态。可设置autocomplete属性为"off"来解决。
* disabled————用于指定表单控件是否可用于交互。特别的是，在禁用了的控件中，点击事件将不被分发。同样，一个禁用了的控件的值不会与表单中其他控件的值一起被提交。（对于FireFox中的一个bug，可参照autocomplete属性中的注2）
* form————用于指定 INPUT 元素所关联的 FORM 元素。该属性的值必须是当前文档的一个 FORM 元素的id属性值。如果不指定form属性，该 INPUT 元素必须是一个 FORM 元素的后代。该属性的使用目的就是为了使 INPUT 元素可放置于文档的任意位置而不必成为 FORM 元素的子元素。当然，一个 INPUT 元素只能关联一个 FORM 元素。(HTML5)
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
```html
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
      // 在控制台中打印该目录的所有文件的信息
      console.table(table);
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

## INS
```html
<ins>This text has been inserted</ins>
```
用于表示一些被添加(插入)到一个文档的文本。与 DEL 元素相对。
* cite————用于指定这些变化（为何需要插入这些文本）的解释资料的URI。例如一个会议纪要的链接(a link to meeting minutes)或者一个故障诊断系统的客服(a ticket in a troubleshooting sytem)。
* datetime————用于指定变化的日期和时间。值必须是一个有效的日期（时间是可选的）字符串。如果值不能被解析为一个可附带时间的日期的字符串，那么 INS 元素不会拥有一个管理的时间戳。

## KBD
```html
<!--单独使用-->
<p>
  使用命令 
  <kbd>help mycommand</kbd>
  查看"mycommand"命令的文档。
</p>
<!--对应串联场景(1)-->
<p>
  你也可以用快捷键
  <kbd>
    <kbd>Ctrl</kbd>
    +
    <kbd>N</kbd>
  </kbd>
  创建一个新的文档。
</p>
<!--对应串联场景(2)-->
<p>If a syntax error occurs, the tool will output the initial command you typed for your review:</p>
<blockquote>
  <samp>
    <kbd>custom-git ad my-new-file.cpp</kbd>
  </samp>
</blockquote>
<!--对应串联场景(3)-->
<p>
  To create a new file, choose the menu option
  <kbd>
    <kbd>
      <samp>File</samp>
    </kbd>
    ⇒
    <kbd>
      <samp>New Document</samp>
    </kbd>
  </kbd>
  .
</p>
<p>
  Don't forget to click the
  <kbd>
    <samp>OK</samp>
  </kbd>
  button to confirm once you've entered the name of the new file.
</p>
```
HTML键盘输入元素(KeyBoarD)。用于提示用户应当或可以从一个键盘、语音设备或者任何其他文本输入设备输入指定的文本。该元素包含的文本默认以内联文本、浏览器的monospace字体（尽管这一点没有被HTML标准授权）为样式进行显示。
* KBD 元素可能被嵌套在 SAMP 元素（Sample Output）形成不同的组合，从而基于视觉线索表示各种输入形式或不同的输入内容。
* 这个元素只有全局属性。
* 注意事项：
* 1、其他元素可以与 KBD 元素串联着使用以表示更多的专门场景。当然，单独使用 KBD 元素也是有效的。
  * (1): 一个 KBD 元素嵌套在另外一个 KBD 元素中表示一个实际的键(键盘上的某个键)或者该输入机制下的某个单位输入。
  * (2)：在 SAMP 元素中嵌套一个 KBD 元素表示系统对用户输入回应的结果。
  * (3)：在 KBD 元素中嵌套一个 SAMP 元素表示用户接下来的输入应当基于系统的输出。例如菜单或者菜单项的名称、显示在屏幕上的按钮的名称。

## KEYGEN
被废弃了。勿用。

## LABEL
```html
<label>
  Click me 
  <input type="text">
</label>
```
表示用户界面中一个项目的标题。
* for————指定在同一文档中的可标记的form相关元素的id。在文档中，第一个符合这样条件的控件（其id匹配 LABEL 元素的for属性的值）是被该 LABEL 元素所标记的控件。LABEL 元素也可以在拥有for属性的同时，包含这一个控件元素（只要for属性指向该控件元素即可）。
* 注意事项：
* 1、一个 LABEL 元素可以通过包含一个控件或者使用for属性来关联一个控件。一个 INPUT 元素则可以与多个 LABEL 元素进行关联。
* 2、LABEL 元素自身不会直接与表单进行关联。它们仅仅通过与它们关联的控件来间接关键表单。
* 3、当一个 LABEL 元素被点击或触碰时，若它关联了一个表单控件，则click事件也会出现在所关联的控件上。

## LEGEND
```html
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

## LI
```html
<ol>
  <li value="3">third item</li>
  <li>fourth item</li>
  <li>fifth item</li>
</ol>
```
常常用于代表一个列表中的一项。
* LI 元素必须被包含在一个有序列表(OL)、一个无序列表(UL)、一个菜单(MENU)中。在菜单和无序列表中，列表项常常用着重点（实心圆点）来展示。在有序列表中，它们则常常在左边带有一个升序的计算器，例如一个数字或字母。
* value————值为一个整数，用于指定在 OL 元素中的当前列表项的原始值。不管列表是以罗马数字或字母来展示，该属性允许的值只能是一个数字。从该项开始的列表项将以该整数为始点进行递增（如果后面的列表项不包含value属性的话）。该属性对 UL 或 MENU 元素的列表没意义。该属性在HTML4规范中被移除，但在HTML5规范中又被重新引入。另外，在Gecko 9.0之前的版本，负值会被不正确地转换为0，但从Gecko 9.0开始，所有整数值都能被正确地解析。

## LINK
```html
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

## MAIN
```html
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

## MAP
```html
<map name="primary">
  <area shape="circle" coords="75,75,75" href="left.html">
  <area shape="circle" coords="275,75,75" href="right.html">
</map>
<img usemap="#primary" src="https://placehold.it/350x150" alt="350 x 150 pic">
```
与 AREA 元素共同使用以定义一个图片地图（image map），即一个可点击的链接区域。
* name————用于给地图（map）一个名称，这样它就能被关联了。该属性是必须出现的，而且必须有一个非空值（值也不能带有空格字符）。同一个文档中，同样的 MAP 元素中，该属性值不能(经过小写转换后)是同样的。如果id属性也存在，那么id和name的值必须是一模一样的。

## MARK
```html
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

## MENU
废弃元素，不要使用。

## MENUITEM
废弃元素，不要使用。

## META
```html
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

## METER
```html
<p>
  Heat the oven to 
  <meter low="150" high="300" min="200" max="500" value="350">350 degrees</meter>
  .
</p>
```
用于表示一个已知范围中或一个片段值中的一个标量值（跟向量值相对）。
* value————当前的数字值。如果设置了最小值（min 属性）和最大值（max 属性），该值必须位于最小值和最大值之间，否则会自动调整到这个区间的端点。如果没指定或指定的值不符合要求，则值为"0"。
* min————值域的较低边界数值。如果元素指定了max的值，则必须小于最大值。默认值为"0"。
* max————值域的较高边界数值。如果元素指定了min的值，则必须大于最小值。默认值为"1"。
* low————用于表现数值相对较低的视觉效果。值必须大于min的值以及小于max、high的值。当value位于min与low所形成的区间时，元素 METER 会表现出当前数值相对较低的视觉效果（例如在Chrome中显示红色填充）。若不指定该属性，其值默认等于min的值。
* high————用于表现数值相对较高的视觉效果。值必须小于max的值以及大于min、low的值。当value位于high与max所形成的区间时，元素 METER 会表现出当前数值相对较高的视觉效果（例如在Chrome中显示绿色填充）。若不指定该属性，其值默认等于max的值。
* optimum————用来指示最优/最佳取值。它必须在正确的值域内（由最小值属性和最大值属性定义）。当使用了low和high属性时，它指明哪一个取值范围是更好的。例如，假设它介于最小值和low之间，那么lower区间就被认为是更佳的取值范围。
* form————用来将 METER 元素与一个 FORM 元素（与该 METER 元素相关）连结起来。例如，一个 METER 元素可能被用于展示一个type为number的 INPUT 元素的值的范围。如果该 METER 元素本身属于 FORM 元素的后代，则可省略该属性。

## NAV
```html
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

## NOSCRIPT
```html
<noscript>
  <!-- anchor linking to external file -->
  <a href="https://www.mozilla.com/">External Link</a>
</noscript>
<p>Rocks!</p>
```
用于定义插入到不支持脚本类型或暂时关闭脚本功能的 HTML 文档中的内容。当浏览器支持脚本执行时，NOSCRIPT 的内容不会出现在文档中；反之，NOSCRIPT 的内容便会添加到文档中并显示。
* 这个元素只有全局属性。

## OBJECT
```html
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

## OL
```html
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
* 3、OL 和 UL 都代表了一堆条目的列表。不同之处在于，对于 OL 元素而言，顺序是有意义的。至于决定使用哪一个，可以这么考虑：尝试改变各项的顺序，如果整个列表的意思改变了，则应该使用 OL 标签，反之，使用 UL 是比较合适的。

## OPTGROUP
```html
<select>
  <optgroup label="Group 1">
    <option>Option 1.1</option>
  </optgroup> 
  <optgroup label="Group 2">
    <option>Option 2.1</option>
    <option>Option 2.2</option>
  </optgroup>
  <optgroup label="Group 3" disabled>
    <option>Option 3.1</option>
    <option>Option 3.2</option>
    <option>Option 3.3</option>
  </optgroup>
</select>
```
用于在 SELECT 元素内创建一组选项（options）。
* disabled————如果设置了该布尔属性，组中的每一个选项都不可选。通常浏览器会使这样的控件变灰，从而使其无法接收任何浏览事件，如鼠标点击、获取焦点等。
* label————该组选项的名称。当在其他用户界面标记该组选项时浏览器会用到。如果该元素被使用，该属性是强制要求定义的。
* 注意事项：
* 1、OPTGROUP 元素不应当嵌套使用。

## OPTION
```html
<!-- The second value will be selected initially -->
<!--Supplement an id here instead of using 'text'-->
<select name="text">
  <option value="value1">Value 1</option> 
  <option value="value2" selected>Value 2</option>
  <option value="value3">Value 3</option>
</select>
```
用于在 SELECT、OPTGROUP 或 DATALIST 标签中定义一个选项。就其本身而言，OPTION 元素可以在一个HTML文档中表示弹出框中的菜单项以及其他条目列表。
* disabled————如果设置了该布尔属性，该项将变成不可选的。通常浏览器会使这样的控件变灰，从而使其无法接收任何浏览事件，如鼠标点击、获取焦点等。如果其祖先元素 OPTGROUP 设置了disabled属性，即使本 OPTION 不设置该属性，也会变得不可用。
* label————其文本值用于指出该项的意思。如果该属性没有定义，则 OPTION 元素包含的文本内容将作为label属性的值。
* selected————若出现该布尔属性属性，则表明该选项在开始时是被选中的。如果 OPTION 元素是一个 SELECT 元素的后代，而 SELECT 元素又没有设置multiple属性的话，那么该 SELECT 元素的后代 OPTION 元素中只有一个可以拥有selected属性。
* value————该属性的内容表示当本 OPTION 被选中时，其在表单中将被提交的值。如果省略了该属性，则 OPTION 元素包含的文本内容将作为value属性的值。

## OUTPUT
```html
<!--output将显示名称为a和b的控件的值的和，可尝试改变这两控件的值，会发现output元素的值会随之改变-->
<form oninput="result.value=parseInt(a.value)+parseInt(b.value)">
  <input type="range" name="b" value="50" /> +
  <input type="number" name="a" value="10" /> =
  <output name="result">60</output>
</form>
```
一个容器元素。用于网站或APP中注入一个计算的结果或一个用户动作的输出。
* for————值为其他元素的ID的值所组成的列表。指定那些元素可以提供输入值到计算中（或者说影响计算）。
* form————指定与 OUTPUT 元素关联的 FROM 元素（即本 OUTPUT 元素属于哪一个 FORM 元素）。值为在同一个文档中的 FORM 元素的ID值。如果没定义该属性，则 OUTPUT 元素必须是一个 FORM 元素的后代。
* name————本 OUTPUT 元素的名称。

## P
```html
<p>This is the first paragraph of text.
  This is the first paragraph of text.</p>
<p>This is the second paragraph.
  This is the second paragraph.</p>
```
用于展示一段文本。段落通常显示为与相邻文本块由垂直空白空间分割（即换行）或首行缩进的文本块。段落是块级元素。
* 这个元素只有全局属性。
* 注意事项：
* 1、align属性已经废弃。不要再使用它。

## PARAM
```html
<!-- Embed a flash movie with parameters -->
<object data="movie.swf" type="application/x-shockwave-flash">
  <param name="foo" value="bar">
</object>
```
用于为 OBJECT 元素定义参数。
* name————参数的名称。
* value————为产生指定的值。

## PICTURE
```html
<!--通过media属性指定一个媒体查询，用户代理将根据屏幕尺寸决定是否选择该 SOURCE 元素。若媒体查询的结果为false，则 SOURCE 元素将被忽略-->
<picture>
  <source srcset="mdn-logo-wide.png" media="(min-width: 600px)">
  <img src="mdn-logo-narrow.png" alt="MDN">
</picture>
<!--通过type属性为 SOURCE 元素指定一个MIME类型。如果用户代理不支持该给定类型，则 SOURCE 元素会被忽略-->
<picture>
  <source srcset="mdn-logo.svg" type="image/svg+xml">
  <img src="mdn-logo.png" alt="MDN">
</picture>
```
作为零个至多个 SOURCE 元素以及后面跟着一个 IMG 标签的容器，以提供一张图片的不同尺寸版本。浏览器会根据每个 SOURCE 元素的所提供的图片来选择一张匹配得最好的，显示在 IMG 标签所占据的网页空间。如果没有匹配到合适的，则直接显示 IMG 标签所声明的图片（相当于回退功能）。为了选择到合适的图片，用户代理（浏览器）会检查每一个 SOURCE 元素的scrset、media和type属性，以匹配网页的当前布局、显示设备的特点等等。
* 这个元素只有全局属性。
* 注意事项：
* 1、可以使用object-position属性在元素的框框内调整图片的定位。可以使用object-fit属性来控制图片以调整其在框框大小。

## PRE
```html
<!--显示CSS代码-->
<pre>
body {
  color:red;
}
</pre>
```
用于原样显示写在HTML中（在 PRE 元素内）的文本。元素内部的文本默认以“非等比”字体(例如 等宽字体)渲染。空白（空格、制表符、回车）会原样显示，不会删减。
* 这个元素只有全局属性。

## PROGRESS
```html
<progress value="70" max="100">70 %</progress>
```
属于HTML5新引入的元素。用于显示一个任务的完成进度。通常以进度条的形式出现。
* max————描述 PROGRESS 元素所指定的任务需要多少量（即数量）。要求值必须是一个大于"0"且有效的浮点数。默认值为"1"。
* value————描述 PROGRESS 元素所指定的任务完成了多少量（即数量）。要求值必须为"0"至max所指定的值之间。如果max属性被省略了，则value的值为"0"至"1"的闭区间。如果value属性被省略，进度条则变得不确定，意味着某个活动在进行中但不确定要花多长时间。
* 注意事项：
* 1、对于 PROGRESS 元素而言，最小值永远是"0"，因此不允许设置min属性。对于火狐浏览器而言，可以使用CSS属性-moz-orient属性来指定进度条是渲染成水平方向（默认的）还是垂直方向。
* 2、伪类 :indeterminate 可用于匹配模糊的进度条。根据上述，移除 PROGRESS 元素的value属性后（可通过 element.removeAttribute("value") 的方式移除），进度条即变成模糊进度条。

## Q
```html
<p>
  According to Mozilla's website,
  <q cite="https://www.mozilla.org/en-US/about/history/details/">
    Firefox 1.0 was released in 2004 and became a big success.
  </q>
</p>
```
用于表示所包含的文本属于一个很短的内联的引用。大部分现代浏览器都是通过一组引号（通常是双引号）围起文本来实现这一点。该元素用于短引用，因此不需要段落换行。对于长引用而言，用 BLOCKQUOTE 元素更合适一些。
* cite————该属性的值是一个为所引用的信息指明一个源文档或源消息的URL。该属性主要是为了指向解析所引用的文本的上下文的信息。
* 注意事项：
* 1、大部分现代浏览器会自动为一个 Q 元素内的文本加上引号（通常是双引号）。因此，在老旧的浏览器中，可能需要添加相应的样式规则来模拟引号的效果。

## RP
```html
<!--显示每个汉字的读音-->
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
  字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
```
即 Ruby Parentheses 。用于为浏览器在不支持 RUBY 元素显示ruby附注时，提供给浏览器的回退显示机制（通常就是为注释文本添加括号）。一个 RP 元素应当包含一组开闭括号，该括号则含有包含了附注文本的 RT 元素。
* 这个元素只有全局属性。
* 注意事项：
* 1、Ruby注释用于显示东亚字符的读音（正常情况下，该读音会显示在字符的二维上方），例如日本的汉字注音和中国的汉字拼音。RP 元素则用于在浏览器缺失对 RUBY 元素支持的情况下，显示一些字符以表明 RT 的内容，这些字符通常是括号。

## RT
```html
<ruby>
  漢 <rt>Kan</rt>
  字 <rt>ji</rt>
</ruby>
```
即 Ruby Text 。指定一个ruby注解的文本组件，以用于提供发音、翻译或东亚印刷文字的字译信息。该元素必须被包含在一个 RUBY 元素内。
* 这个元素只有全局属性。

## RTC
```html
<div class="info">
  <ruby>
    <rb>旧</rb><rt>jiù</rt>
    <rb>金</rb><rt>jīn</rt>
    <rb>山</rb><rt>shān</rt>
    <rtc>San Francisco</rtc>
  </ruby>
</div>
```
即 Ruby Text Container 。用于包裹 RUBY 元素内的子元素 RB 标签内出现的字符语义附注。RB 元素内可以同时出现发音注解（RT 元素）和语义注解（RTC 元素）。现阶段只有火狐浏览器支持。
* 这个元素只有全局属性。

## RUBY
```html
<!--汉字字符-->
<ruby>
  漢 <rp>(</rp><rt>Kan</rt><rp>)</rp>
  字 <rp>(</rp><rt>ji</rt><rp>)</rp>
</ruby>
<!--日语词组-->
<ruby>
  明日 <rp>(</rp><rt>Ashita</rt><rp>)</rp>
</ruby>
```
用于表示一个ruby注释。ruby注释则用于显示东亚字符的读音。现代浏览器均支持该元素。在英语中，ruby除了作为红宝石的意思，还有细铅字的意思。
* 这个元素只有全局属性。

## S
```html
<!--下面两行文字的显示效果是一样的-->
<s>Today's Special: Salmon</s> 
SOLD OUT<br>
<span style="text-decoration:line-through;">
  Today's Special: Salmon
</span> 
SOLD OUT
```
即 Strikethrough 。渲染的效果就是用一根线来划过所包含的文本。S 元素主要用于表示某些东西不再相关或不再准确。但是 S 元素并不适用于指代文本编辑，DEL 元素更合适些。
* 这个元素只有全局属性。

## SAMP
```html
<!--基础用法-->
<p>
  当这个过程完成后，屏幕将输出文本
  <samp>扫描完成，<em>N</em>个结果被发现</samp>。
  然后你可以继续下一步骤。
</p>
<!--包含用户输入的样例输出-->
<pre>
  <samp>
    <span class="prompt">mike@interwebz:~$</span>
    <kbd>md5 -s "Hello world"</kbd>
    MD5 ("Hello world") = 3e25960a79dbc69b674cd4ec67a72c62
    <span class="prompt">mike@interwebz:~$</span>
    <span class="cursor">█</span>
  </samp>
</pre>
```
即 Sample 。用于包含从一段计算机程序中得出的样例（或援引）输出而成的内联文本。该标签的内容通常用浏览器的默认的等宽字体进行渲染。
* 这个元素只有全局属性。
* 注意事项：
* 1、可用CSS规则（指CSS属性 font-family ）来覆盖浏览器对 SAMP 元素所使用的默认字体。但是，有可能浏览器的优先权会比你使用的CSS样式的优先权要高。
* 2、如果你需要一个容器用于承载你的网站或APP的JavaScript代码的输出结果，你应当使用 OUTPUT 元素进行替代。

## SCRIPT
```html
<!-- HTML4 以及 XHTML 引入外部脚本的方式-->
<script type="text/javascript" src="javascript.js"></script>
<!-- HTML5 引入外部脚本的方式-->
<script src="javascript.js"></script>
```
用于嵌入或引入可执行的代码。通常就用于嵌入或引入JavaScript代码。SCRIPT 元素也可用于其他语言，例如WebGL的GLSL着色编程语言。
* async————该布尔属性用于指定浏览器是否应当（如果可以的话）异步地执行脚本。老旧的浏览器不支持该属性。
* crossorigin————通常情况下，如果 SCRIPT 标签不能通过标准的CORS检查的话，则其会传递极少的信息到window.onerror中。为了允许使用了处于不同域的静态媒体的网站记录到该错误，可使用该属性。
* defer————该布尔属性被设置来指定脚本将在整个文档解析完成后执行。但是，脚本也将在DOMContenLoaded事件触发前执行。为了对动态插入的脚本实现同样的效果，可以对这些脚本使用"async=false"，那么带有defer属性的 SCRIPT 标签的脚本将按照出现在文本的顺序执行。
* integrity————该属性包含着内联元数据以协助用户代理验证所获取的资源是否被篡改过。具体内容可查看： https://developer.mozilla.org/en-US/docs/Web/Security/Subresource_Integrity 。
* nomodule————实验性属性，别用在产品上。该布尔属性被设置来指定脚本是否不应当被支持ES6模块化的浏览器执行。
* nonce————在脚本地址的内容安全策略下的一份白名单。值为一个加密随机数（一个只用一次的数字）。每次服务器传送一份策略时，它都必须生成一个独一无二的nonce值。严格要求所提供的nonce值是不能被猜测的，否则传递一份资源的策略（证书）就变得毫无意义。
* src————用于指定一份外部的脚本。该属性可用于替代在一份文档中直接嵌入一份脚本的方式。
* text————像textContent属性一样，该属性是用于设置 SCRIPT 元素的文本内容的。但又跟textContent属性不同，在文本节点被插入到DOM中后，该属性的内容将作为可执行的代码。
* type————指定脚本代表的类型。可能的值的种类包括，
  * 省略不写或是一个JavaScript的MIME类型：对于兼容HTML5的浏览器而言，这类值就是表明脚本为JavaScript。HTML5规范强制要求网页作者省略该属性而不是提供一个累赘的MIME类型。对于早期的浏览器而言，这类值指定了嵌入或引入的代码（通过src属性）的脚本语言。
  * module：对于兼容HTML5的浏览器而言，该标签内的代码将被看成是一个JavaScript模块。脚本内容的处理过程便不会被charset或defer属性所影响。（HTML5新增）
  * 任意的其他的值：嵌入的内容将被当成一个不会被浏览器处理的数据块。开发者必须使用一个有效的不是一个JavaScript的MIME类型的MIME类型来指代数据块。应用了此类值后，src属性将被忽略。
* 注意事项：
* 1、如果src属性不存在时，async属性一定不能被使用，否则async属性会完全不起作用。
* 2、动态插入的脚步默认是以异步的方式执行的。所以，如果希望其同步执行（即根据插入的顺序执行），那么应当为其设置"async=false"。
* 3、如果src属性不存在时，defer属性一定不能被使用，否则defer属性会完全不起作用。
* 4、如果一个 SCRIPT 元素已经指定了src属性，那么它的标签内就不应当再嵌有脚本代码。
* 5、在火狐浏览器中，开发者可以在 SCRIPT 标签中通过一个非标准的version参数在type属性中指定JavaScript的版本，例如type="application/javascript;version=1.8"。最新的火狐浏览器（>59）已经去除了该功能。
* 6、不带有async、defer属性的脚本，以及内联脚本，都会在获取后立即执行，执行完毕后才会继续解析后面的页面。
* 7、脚本本应当带有MIME类型"text/javascript"。但浏览器是很宽容的，只有当脚本带上了一个图片类型"image/*"、一个视频类型"video/*"、一个音频类型"audio/*"或"text/csv"时，才会阻塞它们。如果脚本被阻塞住了，那么一个错误事件将被发送到元素中，否则，一个加载完成事件将被发送到元素中。

## SECTION
```html
<!--以前我们这么用-->
<div>
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>
</div>
<!--现在我们这么用-->
<section>
  <h1>Heading</h1>
  <p>Bunch of awesome content</p>
</section>
```
代表了一个独立的部分。要求所包含的内容没有更多语义化上的要求。通常但不是绝对的，SECTION 元素包含有一个头部 HEADING 元素。举例说，一个导航菜单就应当被包裹在一个 NAV 元素中，但是，一组搜索结果或者一份地图显示与控制控件就没有专门的元素去表示，那么它们便能被放置到一个 SECTION 元素中。
* 这个元素只有全局属性。
* 注意事项：
* 1、每个 SECTION 元素都应当能被用户所辨识，通常就是让其包含一个标题（H1-H6 元素）。
* 2、如果将一个 SECTION 元素的内容分别联合起来也是有意义的，那么请使用一个 ARTICLE 元素替代它。
* 3、不要使用 SECTION 标签作为一个通用的容器。这个是 DIV 的职责所在，尤其是当这个部分只是用于赋予样式的目的时。一个很赞的规则是一个部分（SECTION）逻辑上应当出现在一个文档的大纲上。

## SELECT
```html
<!-- The second value will be selected initially -->
<!--Supplement an id here instead of using 'text'-->
<select name="text">
  <option value="value1">Value 1</option> 
  <option value="value2" selected>Value 2</option>
  <option value="value3">Value 3</option>
</select>
```
表示一个提供一组选项的控件。
* autofocus————值为布尔类型，用于指定页面刚加载完成时，某个表单控件是否应当拥有输入焦点（除非用户改变了输入焦点，例如在别的控件中打字��。一个表单只能有一个控件拥有autofocus属性。(HTML5)
* disabled————该布尔属性用于指定用户能否与本控件交互。如果没指定该属性，本控件将从包含它的元素（例如 FIELDSET 元素）继承相关的设置。如果祖先元素也没有设置disabled属性，那么本控件就是可与用户交互的。
* form————用于指定 SELECT 元素所关联的 FORM 元素。该属性的值必须是当前文档的一个 FORM 元素的id属性值。该属性的使用目的就是为了使 INPUT 元素可放置于文档的任意位置而不必成为 FORM 元素的子元素。(HTML5)
* multiple————该布尔属性用于指定在列表中可以选中多个选项。如果 SELECT 元素没指定该属性，则一次只有一个选项能被选中。
* name————指定本控件的名称。
* required————该布尔属性用于指定一个带有非空字符串值的选项必须被选中。(HTML5)
* size————如果本控件以一个可滚动列表盒子的形式出现，那么该属性表示选项列表中一次应显示的行数。浏览器并没有要求一个 SELECT 元素显示为一个滚动列表盒子。默认值为"0"。
* 注意事项：
* 1、根据HTML5规范，size属性的默认值应当为"1"。但在实际中，这种情况会影响到某些网站，因此暂时没有浏览器支持这一点。
* 2、SELECT 元素的内容是静态的、不可编辑的。

## SHADOW
已废弃，勿用。

## SLOT
```html
<template id="my-paragraph">
  <style>
    p {
    color: white;
    background-color: #666;
    padding: 5px;
    }
  </style>
  <p>My paragraph</p>
  <slot name="my-text">My default text</slot>
</template>
<my-paragraph>
  <ul slot="my-text">
    <li>Let's have some different text!</li>
    <li>In a list!</li>
  </ul>
</my-paragraph>
```
该元素仍然属于实验性元素（IE完全不支持，火狐不支持name属性）。作为网站组件化技术套件的一部分，它是一个网页组件的占位符，可以让开发者在其位置填充所需的标签，从而使得组件实现分离后又能合并到一起显示。
* name———— SLOT 元素的名称。一个命名位置即一个带有name属性的 SLOT 元素。
* 注意事项：
* 1、本元素的具体用法请参考（通常与 TEMPLATE 元素配套使用）： https://developer.mozilla.org/en-US/docs/Web/Web_Components/Using_templates_and_slots 和 https://developer.mozilla.org/en-US/docs/Web/Web_Components 。

## SMALL
```html
<p>This is the first sentence. <small>This whole sentence is in small letters.</small></p>
```
用于使文本字体大小变小（例如使大号字体变成中号，使小号字体变成极小号），到浏览器支持的最小字号为止。在HTML5中，该元素被赋予新的用途，用于表示旁注（）和小号印刷字体，包括版权和法律声明。新用途与它的显示样式是独立的。
* 这个元素只有全局属性。
* 注意事项：
* 1、尽管 SMALL 元素跟 B 和 I 元素一样，可能被认为破坏了"结构与样式分离"的原则，但是这三者在HTML5中都有效。笔者鼓励在是否使用 SMALL 元素还是CSS样式时，做出最优的判断后再进行抉择。

## SOURCE
```html
<!--末行的文字会在浏览器不支持 VIDEO 元素的资源时显示-->
<!--如果浏览器不支持任何 SOURCE 元素中资源，则会触发一个error事件-->
<video controls>
  <source src="foo.webm" type="video/webm">
  <source src="foo.ogg" type="video/ogg"> 
  <source src="foo.mov" type="video/quicktime">
  I'm sorry; your browser doesn't support HTML5 video.
</video>
```
用于为 PICTURE、AUDIO、VIDEO 元素指定多媒体资源。这是一个空元素（不会有子节点）。通常用于为不同浏览器提供一份媒体的不同格式，以实现兼容。
* sizes————实验性属性。是一组描述最终渲染的图片根据源而代表显示的宽度大小的列表。每个源大小由一组逗号分隔的媒体条件长度对组成。这份信息是用于浏览器在显示页面之前决定使用srcset属性中哪一张图片。只有当 SOURCE 元素是一个 PICTURE 元素的直接子元素时sizes属性才会生效。
* src————当 SOURCE 元素属于 AUDIO 和 VIDEO 标签中的子元素时，该属性是必需的。当 SOURCE 元素放置于一个 PICTURE 元素时，该属性的值会被忽略。
* srcset————实验性属性。一组由一个或多个用逗号分隔的字符串组成的列表，用于指定一组可能被浏览器使用的图片。每个字符串的成分由3种成分组合而成，
  * 1、一张图片的URL。
  * 2、一个宽度描述符，即一个正整数后面直接跟着'w'。如果省略该项，则默认值为无限大。
  * 3、一个像素密度描述符，即一个正浮点数后面直接跟着'x'。如果省略该项，则默认值为'1x'。
  * 注1：列表中的每个字符串必须至少有一个有效的宽度描述符或像素密度描述符。
  * 注2：贯穿整个列表，包含相同的宽度描述符和像素密度描述符的元组只能有一个。
  * 注3：浏览器在某一个特定的时间点会选择一张嘴合适的图片来显示。
  * 注4：srcset属性只在 SOURCE 元素是一个 PICTURE 元素的直接子元素时有效。
* type————资源的MIME类型。可选带一个codecs参数。关于如何指定codecs，可参考 https://tools.ietf.org/html/rfc4281 。
* media————实验性属性。资源的预定媒体的媒体查询。该属性只应在 PICTURE 内的 SOURCE 元素中使用。
* 注意事项：
* 1、如果type属性没有指定，媒体的类型就会从服务器中获取，然后就会被检查是否能被用户代理处理。如果该资源不能被渲染，则下一个 SOURCE 元素就会进入检查阶段。
* 2、如果指定了type属性，那么该type属性的值就会被拿来跟可以显示的类型进行比较。如果type的值不能被识别，则不会再从服务器获取下一步的查询，相反，下一个 SOURCE 元素会立即进入检查阶段。

## SPAN
```html
<p>
  <span class="some-styles">Some text</span>.
  Other text.
</p>
```
一个通用的内联容器，天生不代表任何事物。可用于对其他元素进行分组以进行样式渲染（使用class或id属性），或者为组内的元素添加相同的属性值，如lang属性。只有在其他任何元素都不合适时才应使用该元素。它跟 DIV 元素很像，只是 DIV 是块级元素。
* 这个元素只有全局属性。

## STRONG
```html
<p>
  Before proceeding, 
  <strong>make sure you put on your safety goggles</strong>.
</p>
```
用于指定内容具有强烈的重要性、严重性或紧急性。浏览器通常以粗体类型来渲染本元素的内容。
* 这个元素只有全局属性。
* 注意事项：
* 1、STRONG 元素的内容是具有"强烈的重要性"的，包括了巨大严重性或紧急性的东西（例如警告）。这有可能是因为某一句话在整个页面中具有强烈的重要性，又或者是因为开发者仅仅为了指出某些词相对于附近的内容而已具有更强烈的重要性。
* 2、通常该元素默认以粗体字的方式进行渲染。但是，不要仅仅用它来简单地对字体进行加粗（应当使用CSS的属性font-weight实现这一点）。
* 3、使用 B 元素来为特定的没有更高等级重要性的文本吸睛。
* 4、使用 EM 元素标记有着压力强调的文本。通常用于改变一句话的重心（或强调动作、或强调事物），直白说就是改变一句话的语气。
* 5、另外一个适合 STRONG 标签的用途是作为一份页面文本的笔记段落或警告段落的标签。

## STYLE
```html
<style type="text/css">
body {
  color: red;
}
</style>
```
用于包含一个文档或一个文档的某一部分的样式信息。默认地，STYLE 元素内的样式指令是CSS。
* type————该属性定义样式语言为某一个MIME类型（这时不应当指定charset）。该属性是选填的，如果省略了该属性，则其值默认为"text/css"。
* media————该属性定义样式应当使用哪个媒体。值为一个媒体查询。如果省略了该属性，则其值默认为"all"。
* nonce————在样式地址的内容安全策略下的一份白名单。值为一个加密随机数（一个只用一次的数字）。每次服务器传送一份策略时，它都必须生成一个独一无二的nonce值。严格要求所提供的nonce值是不能被猜测的，否则传递一份资源的策略（证书）就变得毫无意义。
* title————该属性用于指定一个替代样式表集合。

## SUB
```html
<!--用于脚注-->
<p>
  According to the computations by Nakamura, Johnson, and Mason
  <sub>1</sub> 
  this will result in the complete annihilation of both particles.
</p>
<!--用于变量下标-->
<p>
  The horizontal coordinates' positions along the X-axis are represented as 
  <var>x<sub>1</sub></var> 
  ... 
  <var>x<sub>n</sub></var>
  .
</p>
<!--用于化学公式-->
<p>
  Almost every developer's favorite molecule is
  C<sub>8</sub>H<sub>10</sub>N<sub>4</sub>O<sub>2</sub>, 
  which is commonly known as "caffeine."
</p>
```
用于单纯的排版，指定行内文本应当显示为下标。下标通常用一个更小的字号在更低的基线上渲染。
* 这个元素只有全局属性。
* 注意事项：
* 1、只应由于排版上需要才使用 SUB 元素。不要仅仅因为显示或展现的原因而用该元素。例如，在企业商标上（的某些图案或文字）使用该元素实现就不合适，此时应使用CSS属性vertical-align来实现，或设置值为"sub"，或设置值为更精确的百分比或其他数字值。
* 2、合适的用例包括但不限于，
  * 1、标记脚注数值。
  * 2、标记数学变量数字的下标。当然，开发者也可以使用MathML语言（ https://developer.mozilla.org/en-US/docs/Web/MathML ）来做到这一点，只是兼容性还不够好。
  * 3、显示一个化学公式的原子的给定数字。

## SUMMARY
```html
<details open>
  <summary>Overview</summary>
  <ol>
    <li>Cash on hand: $500.00</li>
    <li>Current invoice: $75.30</li>
    <li>Due date: 5/6/19</li>
  </ol>
</details>
```
指定一份摘要、说明文字或为一个 DETAILS 元素的公开盒子定义一段铭文（即一直会显示的内容）。点击 SUMMARY 元素会使父元素 DETAILS 不断的打开与关闭。该元素尚不能得到浏览器很好的支持。
* 这个元素只有全局属性。
* 注意事项：
* 1、本元素的内容可以是任何标题内容（H1-H6）、平白文字（即不带有标签）或者可用在段落中的HTML文本。
* 2、一个 SUMMARY 元素一般只用作一个 DETAILS 元素的第一子元素。当用户点击在 SUMMARY 上时，父级元素 DETAILS 将切换为打开或关闭状态，然后一个toggle事件将发送至 DETAILS 元素中以方便开发者监听状态的改变。
* 3、如果一个 DETAILS 元素的第一子元素不是一个 SUMMARY 元素，用户代理会使用一个默认的字符串"Details"（中文状态下则是"详情"）作为公示盒子(disclosure box)的标签。
* 4、在每个HTML规范中，SUMMARY 元素的默认样式都包括了"display: list-item;"。这使得改变或移除标签旁边的默认的公示小部件(disclosure widget)变得有可能（该小部件通常是一个三角形）。
* 5、浏览器厂商尚不能很好的支持该元素（IE跟移动端的Safari完全不支持该元素，除了火狐外的浏览器均不支持修改"display: list-item;"）。因此，该元素未适合引入到产品中去。

## SUP
```html
<!--用于数学公式-->
<p>
  One of the most common equations in all of physics is
  <var>E</var>=<var>m</var><var>c</var><sup>2</sup>.
<p>
<!--用于序号-->
<p>
  The ordinal number "fifth" can be abbreviated in various
  languages as follows:
</p>
<ul>
  <li>English: 5<sup>th</sup></li>
  <li>French: 5<sup>ème</sup></li>
</ul>
```
用于单纯的排版，指定行内文本应当显示为上标。上标通常用一个更小的字号在更高的基线上渲染。
* 这个元素只有全局属性。
* 注意事项：
* 1、只应由于排版上需要才使用 SUP 元素。不要仅仅因为显示或展现的原因而用该元素。例如，在企业商标上（的某些图案或文字）使用该元素实现就不合适，此时应使用CSS属性vertical-align来实现，或设置值为"sup"，或设置值为更精确的百分比或其他数字值。
* 2、合适的用例包括但不限于，
  * 1、展示指数，例如"X的3次方"。当然，开发者也可以使用MathML语言（ https://developer.mozilla.org/en-US/docs/Web/MathML ）来做到这一点，只是兼容性还不够好。
  * 2、显示某些语言中的缩写的"更高级的字母"(superior lettering)。例如法语的单词"mademoiselle"的缩写形式，除了第一个字母是正常显示，其余的则显示成上标形式。
  * 3、代表顺序数字，例如"第4"的数字加英文形式。

## TABLE
```html
<table>
  <tr>
    <th>Name</th>
    <th>Age</th>
  </tr>
  <tr>
    <td>John</td>
    <td>10</td>
  </tr>
</table>
```
用于表示表格类型的数据，即展示在一个由行和列组合成单元格（用于包含数据）的二维表格的信息。
* 注意事项：
* 1、该元素的专有属性（align、bgcolor、border、cellpadding、cellspacing、frame、rules、summary、width）均从规范中移除，不要再使用。

## TBODY
```html
<!--包含 THEAD 和 TBODY-->
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
      <th>Major</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
      <td>Computer Science</td>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
      <td>Russian Literature</td>
    </tr>
  </tbody>
</table>
<!--包含多个 TBODY-->
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th colspan="2">Computer Science</th>
    </tr>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
    </tr>
    <tr>
      <td>4077830</td>
      <td>Pierce, Benjamin</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="2">Russian Literature</th>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="2">Astrophysics</th>
    </tr>
    <tr>
      <td>4100332</td>
      <td>Petrov, Alexandra</td>
    </tr>
    <tr>
      <td>8892377</td>
      <td>Toyota, Hiroko</td>
    </tr>
  </tbody>
</table>
```
用于封装表格行 TR 元素的集合，即作为表格的主体(body)部分。TBODY 元素，跟其兄弟元素 THEAD 和 TFOOT 元素一起，在用于屏幕或打印机或其他可访问目的的渲染时，提供了有用的语义信息。
* 这个元素只有全局属性。
* 注意事项：
* 1、该元素的专有属性（align、char、charoff、valign）均从规范中移除，不要再使用。属性bgcolor只有IE支持，也不应使用。
* 2、如果表格包含了一个 THEAD 块（为了语义化地指定头部行），则 THEAD 块后面必须跟着 TBODY 块。
* 3、如果使用了 TBODY 元素，则表格中不能同时存在直接的 TR 子元素（即 TR 元素只能出现在 TBODY、THEAD、TFOOT 标签内）。
* 4、当打印一份含有多页表格的文档时，即使每页 TBODY 的内容各不相同，每页 THEAD 和 TFOOT 元素所指定的信息也应当保持相同（至少是类似的）。
* 5、当一份表格是出现在屏幕上下文中（例如 window）而屏幕不能大到显示整个表格时，用户代理可能会让用户在同一个父级 TABLE 元素中分别滚动 THEAD、TBODY、TFOOT、CAPTION 的内容。
* 6、开发者可以在一个 TABLE 元素中使用多个 TBODY 元素，只要所有的 TBODY 元素是连续的就好。这使得程序员可在一大表格中将各行分成不同的部分，而每部分可以根据需要采用不同的格式展示。

## TD
```html
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
      <th>Major</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
      <td>Computer Science</td>
    </tr>
  </tbody>
</table>
```
用于定义表格的一个包含数据的单元格。单元格是表格模型的参与者、构造者。
* colspan————值为非负整数。用于指定该单元格跨过多少列。默认值为"1"。如果设置的值大于"1000"时，会被认为是非法的，然后会被重置为默认值"1"。
* headers————该属性包含了一个用空格隔开的字符串的列表，每个字符串分别对应于应用了该 TD 元素的 TH 元素的id属性值。
* rowspan————值为非负整数。用于指定该单元格跨过多少行。默认值为"1"。如果设置的值为"0"，则该 TD 元素会一直跨越到表格部分（包括 THEAD、TBODY、TFOOT 元素）的末尾。如果设置的值大于"65534"，则值会被重置缩减为"65534"。

## TEMPLATE
```html
<table id="producttable">
  <thead>
    <tr>
      <td>UPC_Code</td>
      <td>Product_Name</td>
    </tr>
  </thead>
  <tbody>
    <!-- existing data could optionally be included here -->
  </tbody>
</table>

<template id="productrow">
  <tr>
    <td class="record"></td>
    <td></td>
  </tr>
</template>

<script>
// Test to see if the browser supports the HTML template element by checking
// for the presence of the template element's content attribute.
if ('content' in document.createElement('template')) {
  // Instantiate the table with the existing HTML tbody
  // and the row with the template
  var t = document.querySelector('#productrow'),
  td = t.content.querySelectorAll("td");
  td[0].textContent = "1235646565";
  td[1].textContent = "Stuff";
  // Clone the new row and insert it into the table
  var tb = document.querySelector("tbody");
  var clone = document.importNode(t.content, true);
  tb.appendChild(clone);
  // Create a new row
  td[0].textContent = "0384928528";
  td[1].textContent = "Acme Kidney Beans";
  // Clone the new row and insert it into the table
  var clone2 = document.importNode(t.content, true);
  tb.appendChild(clone2);
} else {
  // Find another way to add the rows to the table because 
  // the HTML template element is not supported.
}
</script>
```
用于一种保持客户端的内容在页面加载时不会被渲染但可以通过JavaScript在运行时不断实例化的机制。
* 这个元素只有全局属性。

## TEXTAREA
```html
<textarea name="textarea" rows="10" cols="50">Write something here</textarea>
```
用于表示一个多行的平白文本编辑控件。
* autocapitalize————非标准属性，只有 IOS 系统的浏览器支持。用于指定该控件能否与如何根据用户输入（编辑）的内容来自动使首字母大写化。以下值能被IOS5以上的系统支持：
  * none：完全禁止自动使首字母大写化。
  * sentences：自动使句子的首字母变成大写的。
  * words：自动使单词的首字母都变成大写的。
  * characters：使所有字母都自动变成大写的。
* autocomplete————这是一个HTML5新增属性。指定文本域元素是否默认被浏览器自动完成值的填写。可能的值有：
  * "off"：指定用户在每次使用文本域时，都必须明确地输入值，又或者文档本身提供自己的自动完成方法（浏览器是不会自动完成输入的）。
  * "on"：浏览器会根据用户以前在改文本域中输入的内容，自动将其输入填充到输入框中。
  * 注1：当 TEXTAREA 元素没有指定autocomplete属性时，浏览器会使用 TEXTAREA 元素所属的 FORM 元素的autocomplete属性。
* autofocus————用于指定页面刚加载完成时，某个表单控件是否应当拥有输入焦点（除非用户改变了输入焦点，例如在别的控件中打字）。一个表单只能有一个控件拥有autofocus属性。(HTML5)
* cols————用于指定文本的可见宽度（每单位指字符的平均宽度）。值必须为一个正整数。在HTML5中，该默认值为"20"。
* disabled————该布尔属性用于指定用户能否与本控件交互。如果不指定该属性，则控件会从包含它的元素（例如 FIELDSET 元素）继承该设置。如果包含它的元素也没设置该属性，那么控件就是可用的。
* form————用于指定 TEXTEREA 元素所关联的 FORM 元素。该属性的值必须是当前文档的一个 FORM 元素的id属性值。如果不指定form属性，该 TEXTEREA 元素必须是一个 FORM 元素的后代。该属性的使用目的就是为了使 TEXTEREA 元素可放置于文档的任意位置而不必成为 FORM 元素的子元素。当然，一个 TEXTEREA 元素只能关联一个 FORM 元素。(HTML5)
* maxlength————用于指定用户可以输入的字符（Unicode编码）的最大数。如果没有为该属性指定有效值，则用户可以输入无限个字符。(HTML5)
* minlength————用于指定用户至少应当输入多少个字符。(HTML5)
* name————本控件的名称。
* placeholder————一个在控件中告诉用户应当输入什么内容的提示。该提示文本的回车或换行在渲染时必须被当作分行符。
* readonly————该布尔属性用于表示用户不能修改本控件的值。跟disabled属性不一样的是，readonly属性不会阻止用户在控件中的点击或选择操作。只读的控件的值仍然能随着表单一起被提交（到服务器）。
* required————指出用户在提交一个表单之前，必须为该控件填充一个值。
* rows————指定本控件的可见行数。
* spellcheck————该属性值设置为"true"时，表示 TEXTAREA 元素需要进行拼写和语法检查。值为"default"时，指定元素根据默认的情况选择相应的检查行为（可能基于父级元素的spellcheck属性值）。值为"false"时，指定元素不应当进行检查。(HTML5)
* wrap————这是一个HTML5新增属性。用于指定本控件如何缠绕文本。可能的值有：
  * hard：浏览器自动插入换行符（CR+LF）以使每行的宽度都不会超过本控件的宽度。前提是必须设定了cols属性。
  * soft：浏览器确保值中的所有换行都由CR+LF对组成，但不会插入任何额外的换行。（默认值）
  * off：类似于"soft"，但会改变控件的面貌为"white-space: pre;"。所以当某行超出cols指定的宽度时，该行将不会包裹，从而该区域变成可以横向滚动的。
* 注意事项：
* 1、Gecko 2.0引入了对可重置大小的文本域的支持。该功能通过CSS属性resize控制。默认上，文本域是可重置大小的。
* 2、从CSS角度来说，一个 TEXTAREA 是一个可被替代的元素。HTML规范并没有指定一个 TEXTAREA 标签的基线在哪里。不同的浏览器把基线设置在了不同的位置。对于Gecko引擎来说，文本域的基线就是里面第一行文本所在的基线。对于其他浏览器来说，文本域的基线可能被设置在了 TEXTAREA 盒子的底部。因此，不要在 TEXTAREA 元素上使用"vertical-align: baseline;"，否则其行为可能变得不可预测。
* 3、跟光栅图片一样，一个文本域是有其内在尺寸的。

## TFOOT
```html
<table>
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Footer content 1</td>
      <td>Footer content 2</td>
    </tr>
  </tfoot>
</table>
```
用于包裹一个行的集合，来定义表格各列的总结、概括。
* 这个元素只有全局属性。
* 注意事项：
* 1、该元素的专有属性（align、char、charoff、valign）均从规范中移除，不要再使用。属性bgcolor只有IE支持，也不应使用。

## TH
```html
<table>
  <tr>
    <th>First name</th>
    <th>Last name</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
  <tr>
    <td>Jane</td>
    <td>Doe</td>
  </tr>
</table>
```
用于定义一组表格单元格的头部（即表头）。该组的确切性质由属性scope和headers定义。
* colspan————该属性的值为一个正整数，用于指定该单元格跨过多少列。默认值为"1"。值大于"1000"时，会自动被缩减为"1000"。
* headers————该属性的值为一组以空格分隔的字符串，每一个对应于关联本 TH 元素的其他 TH 元素的id属性值。
* rowspan————该属性的值为一个正整数，用于指定该单元格跨过多少行。默认值为"1"。值大于"65534"时，会自动被缩减为"65534"。
* scope————该可枚举属性用于指定头部（定义在本 TH 元素中）所关联的单元格集合。可能的值包括：（注意，已经不建议再使用该属性了）
  * row：表头关联到一行中所有的单元格。
  * col：表头关联到一列中所有的单元格。
  * rowgroup：表头关联到一个行组中所有的单元格。这些单元格可以根据 TABLE 元素中的dir属性值而被放置在头部的右边或左边。
  * colgroup：表头关联到一个列组中所有的单元格。
  * auto：自动。
* 注意事项：
* 1、colspan属性在以前是可以设为"0"的，则本 TH 单元格会跨到 COLGROUP 标签里面的最后一个元素。但主流浏览器均不支持"0"值了，因此一般看不到效果。
* 2、rowspan属性在以前是可以设为"0"的，则本 TH 单元格会跨到表格部分（THEAD、THBODY、TFOOT 算是一个表格部分）的最后一个元素。但主流浏览器均不支持"0"值了，因此一般看不到效果。

## THEAD
```html
<table>
  <thead>
    <tr>
      <th>Header content 1</th>
      <th>Header content 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Body content 1</td>
      <td>Body content 2</td>
    </tr>
  </tbody>
</table>
```
用于包裹一个行的集合，来定义表格各列的头部（信息）。
* 这个元素只有全局属性。
* 注意事项：
* 1、该元素的专有属性（align、char、charoff、valign）均从规范中移除，不要再使用。属性bgcolor只有IE支持，也不应使用。

## TIME
```html
<!--简单的使用-->
<p>
  The concert starts at 
  <time>20:00</time>
  .
</p>
<!--含有日期时间值-->
<p>
  The concert took place on 
  <time datetime="2001-05-15T19:00">May 15</time>
  .
</p>
```
用于表示：一个24小时时钟的时刻（或时间）、公历日历上的一个精确日期（带有可选的时间和时区信息）、一个有效的时间片段。
* datetime————用于指定本元素的时间与日期。值必须为一个有效的可带有一个时间字符串的日期字符串。如果该值不能被正确解析，则本元素不会拥有一个相关的时间戳。
* 注意事项：
* 1、本元素是以一个机器可读格式来展示日期与时间的。例如，它可以帮助一个用户代理提供这样的功能：为一个用户的日程表添加一个事件。
* 2、本元素不适用于不能被计算的专用日期。也不适用于用来表示比公历日历更早的日期（因为计算那些日期相当复杂）。
* 3、日期时间值（机器可读的日期时间值），即本元素的datetime属性值，必须以合适的格式来表示。如果本元素没有设置datetime属性，则本元素必须用不能包含任何子孙元素，这时，元素的文本内容（the element's child text content）便是日期时间值。

## TITLE
```html
<title>网页的标题</title>
```
定义所在文档的标题。标题内容通常显示在浏览器的标题栏或网页的TAB栏。它仅能包含文本，所有子标签都会被忽略。
* 这个元素只有全局属性。
* 注意事项：
* 1、TITLE 元素总是用在网页的 HEAD 块中。

## TR
```html
<table>
  <tr>
    <th>First name</th>
    <th>Last name</th>
  </tr>
  <tr>
    <td>John</td>
    <td>Doe</td>
  </tr>
</table>
```
定义表格的一行（单元格集合）。行中的单元格可以是 TD 元素和 TH 元素的混合。
* 这个元素只有全局属性。
* 注意事项：
* 1、该元素的专有属性（align、char、charoff、valign）均从规范中移除，不要再使用。属性bgcolor只有IE支持，也不应使用。

## TRACK
```html
<video controls poster="/images/sample.gif">
  <source src="sample.mp4" type="video/mp4">
  <source src="sample.ogv" type="video/ogv">
  <track kind="captions" src="sampleCaptions.vtt" srclang="en">
  <track kind="descriptions" src="sampleDescriptions.vtt" srclang="en">
  <track kind="chapters" src="sampleChapters.vtt" srclang="en">
  <track kind="subtitles" src="sampleSubtitles_de.vtt" srclang="de">
  <track kind="subtitles" src="sampleSubtitles_en.vtt" srclang="en">
  <track kind="subtitles" src="sampleSubtitles_ja.vtt" srclang="ja">
  <track kind="subtitles" src="sampleSubtitles_oz.vtt" srclang="oz">
  <track kind="metadata" src="keyStage1.vtt" srclang="en" label="Key Stage 1">
  <track kind="metadata" src="keyStage2.vtt" srclang="en" label="Key Stage 2">
  <track kind="metadata" src="keyStage3.vtt" srclang="en" label="Key Stage 3">
  <!-- Fallback -->
  ...
</video>
```
作为媒体元素（AUDIO 或 VIDEO）的子元素，用于指定时控文本轨道（或者称基于时间的数据），例如用来自动处理字幕（subtitles）。轨道的格式为WebVTT（文件后缀为".vtt"），即网络视频文本轨道（Web Video Text Tracks）。
* default————该属性用于指定本轨道应该是可用的除非用户偏好指定了另外一个更合适的轨道。在每个媒体元素中，该属性仅应用在一个 TRACK 元素上。
* kind————指出文本轨道要如何使用。如果省略该属性则默认值为"subtitles"。如果值是无效的，则会使用"metadata"（在早于52版本的Chrome会使用"subtitles"）。可能的关键词有，
  * subtitles：
    * (1)、字幕提供了观看者不能理解的内容的翻译。例如西方电影的中文字幕。
    * (2)、字幕可能包含额外的内容，通常是额外的背景信息。例如《星球大战》中的某些场景的日期时间信息、位置信息等。
  * captions：
    * (1)、隐藏的带有解释意味的字幕（closed captions）提供了一份抄写本或为音频提供了一份翻译。
    * (2)、它可能包含了重要的非言语交际的信息，例如音乐提示或声音效果。它也可能指出提示（cue）的源头（例如 音乐、文本、字符）。
    * (3)、适合耳聋的用户或声音为静音状态时的使用者。
  * descriptions：
    * (1)、视频内容的文本描述。
    * (2)、适合眼瞎的用户或视频为看不见的状态时的使用者。
  * chapters：
    * (1)、当用户导航到该媒体资源时所打算使用的章节标题。
  * metadata：
    * (1)、被脚本使用的轨道。对用户是不可见的。
* label————一个用户可读的（浏览器在列可用的文本轨道时所用到的）文本轨道标题。
* src————轨道（".vtt"文件）的地址。要求值必须为一个有效的URL。该属性为必填。
* srclang————轨道文本数据的语言。值必须为一个有效的BCP 47语言标签。如果kind属性被设置为"subtitles"，则srclang属性必填。
* 注意事项：
* 1、TRACK 标签添加到媒体的数据类型是定义在kind属性中的，可选值有"subtitles"、"captions"、"descriptions"、"chapters"、"metadata"。
* 2、本元素指出了当用户需要其他的数据时包含给浏览器曝露的时控文本的源文本。
* 3、一个媒体元素不能包含多余一个的带有相同kind、srclang、label属性值的 TRACK 元素。

## U
```html
<!--指出拼读错误-->
<p>This paragraph includes a <u class="spelling">wrnogly</u> spelled word.</p>
```
代表了一个内联文本的跨度，以指出其含有非文本注释的方式进行渲染。默认以一个简单的实体下划线来渲染，但可以使用CSS样式进行更改。
* 这个元素只有全局属性。
* 注意事项：
* 1、在HTML5中，U 是"Unarticulated"而非"Underline"的缩写（旧版的指代underline的 U 元素已经被废除），不应误用。如果是为了让文本添加一根下划线，应当用CSS规则"text-decoration: underline;"来实现。
* 2、U 元素的语义为：标记应用了某些非文本格式注释的文本。
* 3、应用场合包括 为拼读错误添加注解、应用一个合适的名字记号来指示合适的中文名、其他注解形式。
* 4、下面再回顾一下各种语义下应如何选择标签：
  * EM：代表压力强调。
  * B：为文本获取注意力。
  * MARK：标记关键词或短语。
  * STRONG：支持有强烈重要性的文本。
  * CITE：标记书籍或其他发行物的标题。
  * I：指代技术术语、字（音）译、想法、西方的船舶名称。
  * RUBY：提供文本注释。
  * U：提供非文本注释。

## UL
```html
<ul>
  <li>first item</li>
  <li>second item</li>
  <li>third item</li>
</ul>
```
表示一个无序列表，常常被渲染为一个子强调符号开头的列表。
* 这个元素只有全局属性。
* 注意事项：
* 1、UL 元素用于组合各项没有数字顺序以及它们的顺序在列表中是无意义的的项目。通常，无序列表项带有一个强调符（有几种形式，包括一个点、一个圈或一个实心方块）。可以通常CSS的list-style-type属性来修改这些强调符的样式。
* 2、在 OL 和 UL 元素中，嵌套列表的深度和更迭是没有限制的。
* 3、OL 和 UL 都代表了项目的列表。不同之处在于，对于 OL 元素而言，顺序是有意义的。至于决定使用哪一个，可以这么考虑：尝试改变各项的顺序，如果整个列表的意思改变了，则应该使用 OL 标签，反之，使用 UL 是比较合适的。

## VAR
```html
<p>A simple equation: <var>x</var> = <var>y</var> + 2 </p>
```
代表一个数学表达式或一段程序上下文中的一个变量。通常以当前字体的斜体字版本显示，尽管该行为是依赖于浏览器的。
* 这个元素只有全局属性。
* 注意事项：
* 1、VAR 元素通常用在 CODE、KBD、SAMP 等元素上下文中

## VIDEO
```html
<!-- 简单的视频案例 -->
<video src="videofile.webm" autoplay poster="posterimage.jpg">
  很抱歉，您的浏览器不支持内嵌视频，但不必担心，您可以<a href="videofile.webm">下载该视频</a>并用您喜欢的视频播放器打开它
</video>
<!-- 带有字幕的视频 -->
<video src="foo.webm">
  <track kind="subtitles" src="foo.en.vtt" srclang="en" label="English">
  <track kind="subtitles" src="foo.sv.vtt" srclang="sv" label="Svenska">
</video>
<!-- 支持多个播放格式的视频 -->
<video width="480" controls poster="https://archive.org/download/WebmVp8Vorbis/webmvp8.gif" >
  <source src="https://archive.org/download/WebmVp8Vorbis/webmvp8.webm" type="video/webm">
  <source src="https://archive.org/download/WebmVp8Vorbis/webmvp8_512kb.mp4" type="video/mp4">
  <source src="https://archive.org/download/WebmVp8Vorbis/webmvp8.ogv" type="video/ogg">
  您的浏览器不支持 HTML5 视频标签。
</video>
```
嵌入一个支持在文档中播放视频的媒体播放器。
* autoplay————该布尔属性用于指定视频在加载数据过程中应否自动播放。该属性的最大用处在于，需要用户操作的情况下才动态创建媒体元素时，可以使用户避免了进一步的操作才能观看媒体内容。
* buffered————通过该属性获取已缓冲的资源的时间段信息。该属性包含一个TimeRanges对象（对象包含length属性、start()方法、end()方法）。
* controls————如果该属性出现在标签中，浏览器便会为读者提供控制条（通常包括音量、进度拖动条、暂停/重播）。
* crossorigin————这是一个HTML5新增属性。表明是否必须使用CORS完成相关图像的抓取。启用CORS的图像在 CANVAS 元素中可以重复使用而不会被污染。允许的值有：
  * 1、anonymous：执行一个跨域的请求（比如，请求头部带有 Origin: HTTP header）。但不发送证书（比如，没有 cookie，没有 X.509 证书，没有HTTP基本的授权认证）。如果服务器没有给源站证书（没有设置Access-Control-Allow-Origin: HTTP头），视频帧会被污染而且它的使用会被限制。
  * 2、use-credentials：一个有证书的跨域请求（比如，请求头部带有 Origin: HTTP header）被发送 （比如，有 cookie, 有 certificate, 有HTTP基本的授权认证）。如果服务器没有给源站发送证书（通过Access-Control-Allow-Credentials: HTTP header），视频帧将会被污染，且它的使用会受限制。
  * 3、不设置该属性：默认不使用CORS发起请求(例如，不会向服务器发送 HTTP 头部信息)，用以防止其在 CANVAS 中的使用。
  * 4、如果值无效，则值会被当成是"anonymous"。
* height————指定 VIDEO 元素块的高度（只支持像素单位，只支持绝对值，不支持百分比）。
* loop————该布尔属性用于指定当播放进度到达视频的结尾时，自动回到开头继续播放。
* muted————该布尔属性用于指定视频中的音频的默认设置。如果出现了该属性，则在初始化时音频是静音的。默认为不静音。
* played————一个TimeRanges对象，表示所有已播放的视频片段。
* preload————可能的值有：
  * "none"：指定声音不应当自动加载。
  * "metadata"：指定只自动加载声音的元数据（例如声音长度信息）。
  * "auto"：自动加载整个声音文件。
  * ""：跟"auto"一样。
  * 注1：如果设置了autoplay属性，preload属性则无效。
  * 注2：规范并没有强迫浏览器遵循该属性的值。这仅仅是一个参考。
* poster————一个URL，用于指定用户播放该视频前的封面。如果不指定该属性，则在视频的第一帧可用前，什么也不会显示在界面上。当第一帧下载完毕后，将作为封面帧。
* src————被嵌入的视频的URL。这是一个可选属性。因为开发者可在 VIDEO 标签内使用 SOURCE 元素来指定嵌入的视频。
* height————指定 VIDEO 元素块的宽度（只支持像素单位，只支持绝对值，不支持百分比）。
* playsinline————该布尔属性用于指定视频以“内联的方式”播放，即元素播放的播放区域在一行之内。注意该属性的缺少并不意味着视频总会以全屏的方式播放。
* 注意事项：
* 1、也可用 VIDEO 元素播放音频内容，但 AUDIO 元素能提供更好的用户体验。
* 2、对于用户而言，自动播放音频或带有音轨的视频是一个很不好的体验，应尽量避免。如果必须这么做，则应为用户提供一个打开/关闭选项。
* 3、如果要禁止视频自动播放，设置autoplay="false"是没用的。只要 VIDEO 视频标签中出现autoplay属性，视频便会自动播放。应当直接移除autoplay属性来移除自动播放功能。
* 4、各浏览器支持的视频格式在这 https://developer.mozilla.org/en-US/docs/Web/HTML/Supported_media_formats 。因此，应提供一个视频的多种格式来实现兼容性。
* 5、指定一个视频源时，可使用src属性或内嵌 SOURCE 元素，浏览器会根据需要选出最合适的一个。
* 6、可以使用CSS的object-position属性来调整视频在元素框内的位置，可以使用CSS的object-fit属性来控制框内的视频的大小。

## WBR
```html
<!-- 显示的结果为网页右边 456,123 -->
<div dir=rtl>123,<wbr>456</div>
<!-- 显示的结果为网页右边 123,456 -->
<div dir=rtl>123,456</div>
<!-- 避免符合结尾处换行 -->
<p>http://this<wbr>.is<wbr>.a<wbr>.really<wbr>.long<wbr>.example<wbr>.com/With<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages<wbr>/deeper<wbr>/level<wbr>/pages</p>
```
表示一个单词换行机会。指文本中一个浏览器可以拿来换行的位置，虽然浏览器不一定在该位置实现换行。
* 这个元素只有全局属性。
* 注意事项：
* 1、在UTF-8编码的网页中，WBR 元素的行为就像"U+200B"、"ZERO-WIDTH SPACE"（0长度空格）编码点一样。
* 2、特别的是，该标签的行为很像一个bidi BN的Unicode编码点，意味着它在双向排序中不构成影响。（实测是有影响的，例子请看前面的HTML代码）
* 3、《雅虎样式向导》（The Yahoo Style Guide）推荐在URL的标点符号前换行，以免在URL较长的情况下，用户在看到该URL的第一行时误以为到了URL的终点。
* 4、出于相同原因，WBR 元素不会在换行的地方引入连字符。为了使连字符仅仅在行尾出现，使用连字符软实体(&shy;)来代替。
* 5、该元素早在 IE5.5 时代就被实现了，只是HTML5正式将其引起官方标准。