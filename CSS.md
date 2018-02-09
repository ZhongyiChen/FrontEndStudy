/***以下就是所有的CSS属性啦！！！！***/

#   position:
一共有5个值：static | relative | absolute | fixed | inherit
该属性定义建立元素布局所用的定位机制。任何元素都可以定位，不过绝对或固定元素会生成一个块级框（BFC），而不论该元素本身是什么类型。
relative————
    （1）相对定位元素会相对于它在正常流中的默认位置偏移。
    （2）当元素的z-index为一个具体的数值（包括0）而不是auto时，设置了relative后会使元素新建层叠上下文，即元素的子元素层级会被该元素所约束。
absolute————
    （1）绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。
    （2）子元素设置了absolute定位时，其父级元素的 overflow 属性无法对该子元素进行有效约束。但父级元素再设置relative定位时，会把该子元素的超出部分切掉。
    （3）单纯设置元素的 position 为 absolute 时，元素只是浮动到原来位置的z轴上方（此时 left、top等需为 auto ），而余下的static元素则形成新的文档流。
    （4）考虑到重绘与回流的问题，动画尽量作用在绝对定位元素上！
    （5）如果元素是block水平的，当应用了absolute绝对定位后，依然是换行显示的。即前面一行文字不会被挡住。
    （6）如果元素是inline/inline-block水平的，当应用了absolute绝对定位后，依然保持在前面文字的后面，从而在x轴上实现了位置跟随。
    （7）例子，实现盒子的水平垂直居中：	.box{ position: absolute; left: 0; right: 0; top: 0; right: 0; width: 50%; height: 50%; margin: auto; }
        原理：width/height设置的尺寸 要优先于 left/right/top/bottom拉伸的尺寸
static 元素会忽略任何 top、bottom、left、 right 或者 z-index  声明。
inherit规定应该从父元素继承 position 属性的值。
#   top:
若元素为 static 元素，该属性无效。
可使用负值。
若元素为 absolute 元素，则可以结合 bottom 属性对元素进行高度的拉伸。top的百分比值是根据所定位的父容器的高度进行计算的。
若元素为 relative 元素，则会导致声明的 bottom 无效。top的百分比值是根据父容器的高度进行计算的。
#   bottom:
若元素为 static 元素，该属性无效。
可使用负值。
百分比值与top同理。
#   left:
若元素为 static 元素，该属性无效。
可使用负值。
若元素为 absolute 元素，则可以结合 right 属性对元素进行宽度的拉伸。left的百分比值是根据所定位的父容器的宽度进行计算的。
若元素为 relative 元素，则会导致声明的 right 无效。left的百分比值是根据父容器的宽度进行计算的。
#   right:
若元素为 static 元素，该属性无效。
可使用负值。
百分比值与left同理。
#   z-index:
若元素为 static 元素，该属性无效。
可使用负值，支持CSS3 animation动画。
两个定位元素的覆盖原则————
    如果该两个定位元素z-index没有发生嵌套
	    1、后来居上的原则
	    2、哪个大，哪个上
    如果该两个定位元素中有一个或全部是嵌套在别的元素中时
        1、祖先优先原则
            前提：祖先的z-index值是数值，而不是 auto ！否则就以当前元素的 z-index 为准与另外一个元素的祖先的 z-index 值进行比较
                原因：z-index 为 auto; 当前层叠上下文的生成盒子层叠水平是 0 。盒子(除非是根元素html)不会创建一个新的层叠上下文
什么是层叠上下文————
    层叠上下文(stacking context)是HTML元素中的一个三维概念，表示元素在z轴上有了“可以高人一等”。
具有层叠上下文的元素————
    1、页面根元素。它天生具有层叠上下文，称之为“根层叠上下文”
    2、z-index 值为数值的定位元素也具有层叠上下文。
    3、拥有以下属性的的元素
        （1）z-index值不为auto的flex项(即父元素display:flex|inline-flex。子元素的z-index值不为auto，则子元素会创建层叠上下文)
        （2）元素的opacity值不是1（这个厉害了！当transition动画产生时，opacity未达到1时，会把文字给覆盖掉，直到opacity为1时，文字才可见。在这里，文字与图片同级）
        （3）元素的transform值不为none
        （4）元素mix-blend-mode值不是normal
        （5）元素的filter值不是none（是指CSS3的滤镜哦！）
        （6）元素的isolation值是isolate
        （7）position 为 fixed 声明（blink/webkit内核浏览器支持！）
        （8）will-change指定的属性值为上面任意一个
        （9）元素的-webkit-overflow-scrolling设为touch
什么是层叠顺序————
    层叠顺序(stacking order)是指元素发生层叠的时候有着特定的垂直显示顺序
7阶层叠水平————
    background/border < 负z-index < block块状水平盒子 < float浮动盒子 < inline/inline-block水平盒子 < z-index为auto或看成z-index为0或不依赖z-index的层叠上下文 < 正z-index
z-index与层叠上下文————
	1、定位元素默认 z-index 为 atuo 可以看成是 z-index 为 0 ;
		例如：为何定位元素会覆盖普通元素？原因：当元素拥有定位属性后，隐含的 z-index 为 auto 生效，根据7阶层叠水平可知， z-index 为 auto 的元素是在inline水平元素之上的
	2、z-index不为auto的定位元素会创建层叠上下文
		在父容器div和图片img均为定位元素的情况下，若img的z-index为负值，则会被div的背景颜色覆盖；但是，一旦容器z-index值为数值(包括0)，图片的就覆盖了div的背景色
		上例中，一开始时，div的 z-index 为 auto ，结果img的层叠上下文为html，所以会被div的背景色覆盖。然后，div的z-index因为不再是auto，所以成为了img的层叠上下文
		因此，从层叠顺序上讲，z-index 为 auto 可以看成 z-index 为 0 。但是，从层叠上下文来讲，两者却有着本质差异！（当然，在IE7下，z-index 为 auto 也会创建层叠上下文）
	3、z-index层叠顺序的比较止步于父级层叠上下文（z-index受限于层叠上下文）
		即父级元素与其兄弟元素的z-index大小比较会影响子元素和父元素的兄弟元素(及其子元素)的层叠顺序
z-index与其他CSS属性层叠上下文：非定位元素层叠上下文和z-index的关系————
	1、不支持z-index的层叠上下文元素的层叠顺序均是 z-index 为 auto 级别（请参照7阶层叠水平）
	2、依赖z-index的层叠上下文元素的层叠顺序取决于z-index的值。通过z-index值创建层叠上下文的情况有以下两种：
		（1）position值为relative/absolute或fixed(部分浏览器)
		（2）display为flex|inline-flex容器的子flex项
#   float:
必须记住一点，float 设计的初衷仅仅是为了实现文字环绕效果
浮动元素会生成一个块级框（BFC），而不论它本身是何种元素。
float的感性认知：
	包裹性：
		1、收缩：元素应用了float后，宽度收缩，紧紧地包裹住内容（即元素的宽度收缩到元素内的内容的宽度大小）
		2、坚挺：原来没有高度，但元素应用了float后，元素的高度突然扩展到内容的高度大小
		3、隔绝：元素应用了float后，盒子里面的内容发生了任何事情，都与盒子外的内容无关（BFC）
	破坏性：
		1、子元素应用了float后，父容器塌陷：父容器的高度变为0
如果浮动非替换元素，则要指定一个明确的宽度；否则，它们会尽可能地窄。
假如在一行之上只有极少的空间可供浮动元素，那么这个元素会跳至下一行，这个过程会持续到某一行拥有足够的空间为止。
什么是替换元素？什么是非替换元素？
    HTML中的 img 、input 、textarea 、select 、object 都是替换元素，这些元素都没有实际的内容。其余大多数像 div 、p 就是不可替换元素，里面可以放置内容。
具有包裹性（BFC特性）的其他属性：
	display 为 inline-block/table-cell
	position 为 absolute/fixed/sticky
	overflow 为 hidden/scroll
具有破坏性的其他属性：
	display 为 none
	position 为 absolute/fixed/sticky
清除float对其他元素所带来的影响：
	1、float元素底部插入一个带有 clear 为 both; 属性的元素
		1、底部放置一个HTML block水平元素 - < div style="clear: both;"></ div>
		2、CSS after（IE8+）伪元素底部生成 - .clearfix:after{ clear: both; }
	2、父元素BFC化（IE8+）或 haslayout（IE6/7）
BFC/haslayout的通常声明
	1、float 为 left/right
	2、position 为 absolute/fixed
	3、overflow 为 hidden/scroll（IE7+）
	4、display 为 inline-block/table-cell（IE8+）
	5、width/height/zoom 为 1/...（IE6/7）
如何清除浮动？综上，IE8以上浏览器使用：
    .clearfix:after{ content: ''; display: block; height: 0; overflow: hidden; clear: both; }
    .clearfix{ *zoom: 1; }
#   display:
display 属性规定元素应该生成的框的类型。
在HTML的顶部，如果规定了 !DOCTYPE，则 Internet Explorer 8 （以及更高版本）支持属性值 "inline-table"、"run-in"、"table"、"table-caption"、
"table-cell"、"table-column"、"table-column-group"、"table-row"、"table-row-group"、以及 "inherit"。
特殊的display值：
box————该元素定义了 display 为 box 后，该元素便变成了内联元素！
       为该元素的子元素设置相应的 box-flex 属性值（正整数）后，那么子元素会按照相应比例分配该元素的宽度。（不需要再设置width）
       当然，子元素也可以设置固定大小的宽度。然后其余的子元素均分该父元素剩余的宽度。
       当然，如果子元素之间有margin，则该父元素的宽度还需要再减去这些margin值，剩余的宽度大小才被子元素分配。
       定义了box的display方式的该元素还拥有以下属性
       box-orient———— horizontal | vertical | inline-axis | block-axis | inherit 。用来确定父容器里子容器的排列方式，是水平还是垂直。
       box-direction———— normal | reverse | inherit 。用来确定父容器里的子容器排列顺序。
       box-align———— start | end | center | baseline | stretch 。表示父容器里面子容器的垂直对齐方式。
       box-pack———— start | end | center | justify 。表示父容器里面子容器的水平对齐方式。
flex————
#   width:
这个属性定义元素内容区的宽度。
auto————默认值。浏览器可计算出实际的宽度。（块级元素会自动撑满容器的宽度）
length————使用 px、cm 等单位定义宽度。
%————非绝对定位元素中，其定义基于包含块（父元素）宽度的百分比宽度。（当然，内联元素不能作为块级元素的容器）
    （块级元素的 width 的百分比值所得到的宽度并不包含自身的 margin-left、padding-left 或 margin-right、padding-right 的属性值，该元素最终占据屏幕的宽度是直接取其父容器的宽度*百分比再加上自身含有的 margin-left、padding-left、margin-right、padding-right 的值。）
     绝对定位元素中，百分比值的大小的 width 是根据所定位的父容器的宽度进行计算的。
inherit————规定应该从父元素继承 width 属性的值。
注意，重复声明该属性时，后声明的值会覆盖掉前面声明的值。
#   height:
这个属性定义元素内容区的高度。
auto————默认。浏览器会计算出实际的高度。（所有元素均不会自动撑满容器的高度，而是由内容撑开高度）
length————使用 px、cm 等单位定义高度。
%————基于包含它的块级对象的百分比高度。
    （块级元素的 height 的百分比值所得到的高度并不包含自身的 margin-top、padding-top 或 margin-bottom、padding-bottom 的属性值，该元素最终占据屏幕的高度是直接取其父容器的高度*百分比再加上自身含有的  margin-top、padding-top、margin-bottom、padding-bottom 的值。）
     绝对定位元素中，百分比值的大小的 height 是根据所定位的父容器的高度进行计算的。
inherit————规定应该从父元素继承 height 属性的值。
#   max-width:
max-width 属性不包括外边距、边框和内边距。
不允许指定负值。如果元素的 width 属性值大于该值，则用该值重写 width 。（ max-width 有可能重写 width ，但 min-width 有可能重写 max-width ）
none————默认。不限制元素的最大宽度。（其他关键词 max-content、min-content、fit-content、fill-available 的兼容性不好，输入实验属性，不建议使用，max-height、min-width、min-height同）
length————定义元素的最大宽度值。
%————定义基于包含它的块级对象的百分比最大宽度。
inherit————规定应该从父元素继承 max-width 属性的值。
#   max-height:
max-height 属性不包括外边距、边框和内边距。
不允许指定负值。如果元素的 height 属性值大于该值，则用该值重写 height 。（ max-height 有可能重写 height ，但 min-height 有可能重写 max-height ）
none————默认。不限制元素的最大高度。
length————定义元素的最大高度值。
%————定义基于包含它的块级对象的百分比最大高度。
inherit————规定应该从父元素继承 max-height 属性的值。
#   min-width:
不允许指定负值。如果元素的 width（包括max-width）属性值小于该值，则用该值重写 width 。（ max-width 有可能重写 width ，但 min-width 有可能重写 max-width ）
none————默认。不限制元素的最小宽度。
length————定义元素的最小宽度值。
%————定义基于包含它的块级对象的百分比最小宽度。
inherit————规定应该从父元素继承 min-width 属性的值。
#   min-height:
不允许指定负值。如果元素的 height 属性值小于该值，则用该值重写 height 。（ max-height 有可能重写 height ，但 min-height 有可能重写 max-height ）
length————定义元素的最小高度值。（默认值为0）
%————定义基于包含它的块级对象的百分比最小高度。
inherit————规定应该从父元素继承 min-height 属性的值。
#   padding:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
对于block水平元素，padding是会增加元素的尺寸的（即width为非auto时，padding一定会影响尺寸）！
但是！当元素设置了 width:auto 或者元素声明了 box-sizing:border-box 时，
    则在一定程度下，padding不增加元素的尺寸，而是把元素的width变小了！
    然而当padding值过大时，还是会增加元素的尺寸的，内部的内容则按最小宽度显示！
对于inline水平元素，水平padding影响尺寸，但垂直padding不影响尺寸！
	但是！垂直padding是会影响元素的背景色区域的（即垂直padding会影响inline盒模型的content-area区域的大小）！
		可以利用inline元素的垂直padding来实现高度可控的分隔线
			方法：注册 < span></ span> 退出登录	span{padding:16px 6px 1px; margin-left:12px; border-left:2px solid; font-size:0;}//就可以实现一条高为16px的分隔线
所有的input/textarea输入框都内置了padding
所有的button按钮都内置了padding（button的padding是最难控制的！）
    设置 padding:0 时，在Firefox下的button的左右端依然有padding！（解决办法 button::-moz-focus-inner{padding:0;} ）
    在IE浏览器下，button内部的文字越多，左右padding会逐渐变大！（解决办法 button{overflow:visible;} ）
在各个浏览器下，padding与高度的计算并不兼容。
部分浏览器的select下内置了padding，如Firefox。IE8+可以设置padding。
所有浏览器下，radio/checkbox 单复选框无内置padding。
#   padding-top:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   padding-right:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   padding-bottom:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   padding-left:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   border:
简写属性，在一个声明设置所有的边框属性。
可按顺序设置 border-width border-style border-color 此三个属性（忽略其中某一个也是可以滴）
inherit————规定应该从父元素继承 border 属性的设置。
#   border-collapse:
此属性用于设置表格的边框是否被合并为一个单一的边框，还是象在标准的 HTML 中那样分开显示。
要注意，如果没有规定 !DOCTYPE，则 border-collapse 可能产生意想不到的结果。
separate————默认值。边框会被分开。不会忽略 border-spacing 和 empty-cells 属性。
collapse————如果可能，边框会合并为一个单一的边框。会忽略 border-spacing 和 empty-cells 属性。
inherit————规定应该从父元素继承 border-collapse 属性的值。
#   border-top:
简写属性，在一个声明设置顶部边框的属性。
（请参考border）
#   border-right:
（请参考border-top）
#   border-bottom:
（请参考border-top）
#   border-left:
（请参考border-top）
#   border-color:
border-color的默认颜色就是color！（当没有指定border-color、box-shadow、text-shadow...时，会使用color作为边框色！）
支持 transparent 值
    透明边框：使用超级广泛，谁让它始于IE7呢！(相比较之下，color的transparent值要在IE9才开始兼容)
#   border-image:
（该属性在 IE11+浏览器 下支持）
设置这个值的前提是设置了有效的 border 属性。
border-image 属性是一个简写属性，用于设置以下属性：
border-image-source————设置在边框的图片的路径。
border-image-slice————图片边框向内偏移的大小，即剪裁位置。该值是没有单位的（只能是像素值或百分比值）
border-image-width————图片边框的宽度。（可设置的值跟border-width一样）
border-image-outset————边框图像区域超出边框的量。（像素值或百分比值）
border-image-repeat————图像边框是否应平铺(repeated)、铺满(rounded)或拉伸(stretched)。（可分为水平方向和垂直方向）
//图片是被用 # 的方式进行分割的，下面的语句表示图片上下边的分隔线为0px，左右两端的分割线为12px，并且上下左右均是用拉伸的方式进行填充边框。
例如：   border-image：url(img/1.png) 0 12 0 12 stretch stretch;    //这里忽略了 border-image-slice 、border-image-outset
#   border-top-color:
（请参考border-color）
#   border-right-color:
（请参考border-color）
#   border-bottom-color:
（请参考border-color）
#   border-left-color:
（请参考border-color）
#   border-spacing:
作用于 table 元素。border-spacing 属性设置相邻单元格的边框间的距离（仅用于“边框分离”模式）。
border-spacing：值1[ 值2];
    在指定的两个长度值中，第一个是水平间隔，第二个是垂直间隔。除非 border-collapse 被设置为 separate，否则将忽略这个属性。尽管这个属性只应用于表，不过它可以由表中的所有元素继承。
#   border-style:
solid————(实线)，
dashed————(虚线)，在Chrome和Firefox下其小块的宽高比例为3:1，在IE下则是2:1
double————(双实线), 至少要3px才有效果哦！原因：(0+1+0)(1+0+1)(1+1+1)(1+2+1)(2+1+2)(2+2+2)(2+3+2)...
    实现3道杠图标：{width:120px; height:20px; border-top:60px double; border-bottom:20px solid;}
dotted————(点线)，在Chrome和Firefox下的小点是方形的，在IE下则是圆形的。嘻嘻，可以通过设置很大的border值来实现IE7/8下的border-radius效果哦
inset————(内凹)，已被淘汰
outset————(外凸)，已被淘汰
groove————(沟槽)，已被淘汰
ridge————(山脊)。已被淘汰
#   border-top-style:
（请参考border-style）
#   border-right-style:
（请参考border-style）
#   border-bottom-style:
（请参考border-style）
#   border-left-style:
（请参考border-style）
#   border-width:
border-width不支持百分比！（原因：border本来就不应当能变得很大，与内容高宽度的比例没有意义，还有outline,box-shadow,text-shadow也是）
thin————(1px)，
medium————(默认的,3px)，
thick————(5px)。以上这些，在IE7以下是例外的
#   border-top-width:
（请参考border-width）
#   border-right-width:
（请参考border-width）
#   border-bottom-width:
（请参考border-width）
#   border-left-width:
（请参考border-width）
#   border-radius:
%————border-radius的百分比值是相对于元素占据尺寸的百分比，也就是包含边框、padding后的尺寸。而不是单纯地相对于width/height值。
大值特性：在百分比的单值中，50%已经是最大值了，超过的，就只按50%进行渲染。
border-radius单值实际上是8个属性值的简写。
    border-radius：左上角水平圆角半径大小 右上角水平圆角半径大小 右下角水平圆角半径大小 左下角水平圆角半径大小 / 左上角垂直圆角半径大小 右上角垂直圆角半径大小 右下角垂直圆角半径大小 左下角垂直圆角半径大小;
    “/”前面的值设置其水平半径，“/”后面值设置其垂直半径。
    其具体属性是这样子的 >> border-垂直-水平-radius: 水平 垂直;
等比例特性：就是水平半径和垂直半径的比例是恒定不变的。（不管是百分比值还是px数值）
    这就导致了为矩形的border-radius设置一个超大的px值时，其显示的结果跟设置超大的百分比值的效果是不一样的。（因为水平半径和垂直半径分别为长和宽乘以百分比值而得，导致两者结果不一样）
水平半径：椭圆的水平半径（最大为矩形的宽）
垂直半径：椭圆的垂直半径（最大为矩形的高）
单值时————border-radius只有一个取值时，四个角具有相同的圆角设置，其效果是一致的
双值时————border-radius设置两个值，此时top-left等于bottom-right并且他们取第一个值；top-right等于bottom-left并且他们取第二个值，也就是说元素 左上角和右下角相同，右上角和左下角相同
三值时————border-radius设置三个值，此时top-left取第一个值，top-right等于bottom-left并且他们取第二个值，bottom-right取第三个值
四值时————border-radius设置四个值，此时top-left取第一个值，top-right取第二个值，bottom-right取第三个值，bottom-left取第四个值
#   border-top-right-radius:
border-top-right-radius: [length]  [length];   //右上角    （[length]：由浮点数字和单位标识符组成的长度值。不可为负值。）
[length]  [length] 中第一个值是圆角水平半径，第二个值是垂直半径，如果第二个值省略，那么其等于第一个值，这时这个角就是一个四分之一的圆角，如果任意一个值为0，那么这个角就不是圆角。
#   border-bottom-right-radius:
border-bottom-right-radius: [length]  [length];   //右下角
#   border-bottom-left-radius:
border-bottom-left-radius: [length]  [length];   //左下角
#   border-top-left-radius:
border-top-left-radius: [length]  [length];   //左上角
#   margin:
%————关于百分比值
    若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
    若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
auto————作用机制
	1、block水平元素有时候就算没有设置width和height，也会自动填充(满父级元素)；浮动或绝对定位元素也会自动填充(满第一个拥有定位属性的父元素)
	2、此时，如果block水平元素设置width或height，自动填充特性就会被覆盖。此时，剩余的宽度或高度就有了利用的需要
	3、在第二步的情况下，再设置 margin-right: 100px; margin-left: auto; ，就能实现block水平元素距父元素右边100px。
margin的典型应用场景————
    1、滚动容器内上下留白：不要通过给父容器添加上下padding来实现(浏览器不兼容)，通过给子元素添加上下margin值来实现
    2、宽高2:1的自适应矩形：父容器设置 overflow:hidden; ，子元素设置 margin:50% 。那么，子元素上方就可以形成一个宽高为2:1的矩形
	3、宽高1:1的自适应矩形：父容器设置 overflow:hidden; ，子元素设置 margin:100% 。那么，子元素上方就可以形成一个宽高为1:1的矩形
    4、巧用margin重叠：给列表中的每一项都设置相等的margin-top和margin-bottom值，使页面更具健壮性，即最后一个元素移除或位置调换，均不会破坏原来的布局
margin无效情形解析：
	1、inline水平元素的垂直margin无效（有两个前提：一、非替换元素，例如，不是< img>元素；二、正常书写模式）
	2、display:table-cell/table-row 等声明的margin无效
		（注意，FireFox：table-cell类型inline-block的渲染行为；IE：table-cell类型也是table-cell的渲染行为）
	3、绝对定位元素的非定位方位的margin值"无效"。（即例如它没有设置left，则margin-left无效）
		（注意，绝对定位的margin值其实一直有效 [为父元素设置定位即可看到效果]，只是不像普通元素那样，可以和兄弟元素那样重叠在一起）
	4、当元素的左边拥有浮动的图片时，margin-left实际上是相对于父级元素而言，所以当margin-left小于浮动图片的占据尺寸时，是无法看到效果的
	5、元素的内联特性导致的margin无效：例如为一张图片设置margin-top的负值时，图片(以底部为标准)最多只能移动到文字的基线位置（文字是不可能跑到父级容器外部的，最多只跟着图片移动到顶部）
#   margin-top:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   margin-right:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   margin-bottom:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   margin-left:
若该元素的position属性值为absolute或fixed，那么其百分比值的计算是根据所定位的父容器的宽度进行计算的。
若该元素的position属性值为relative或static，那么其百分比值的计算是根据父容器的宽度进行计算的。
#   overflow:
visible————（默认，正常显示超出的内容）
hidden————（隐藏超出的部分）
scroll————（直接添加滚动条）
auto————（不超出容器时，正常显示，一旦超出容器后则显示滚动条）
inherit————（IE8+）
overflow-x、overflow-y：
    如果overflow-x与overflow-y的值相同，则两者加起来等同于overflow
    如果它们的值不相同，要是其中一个被设置成hidden或scroll或auto，另外一个被设置为visible，则visible会被重置为auto
overflow起作用的前提：
	1、元素非 display：inline; 水平
	2、元素要有对应方位的尺寸限制。width/height/max-width/max-height/absolute拉伸 等。
滚动条出现的条件：
	1、< html>< textarea>天生拥有 overflow: scroll/auto; 属性
	2、元素被设置了 overflow: auto; 或 overflow: scroll; 属性，而且内容超出了元素的尺寸限制
水平居中跳动问题的修复
	1、html{ overflow-y: scroll; }
	2、.container{ padding-left: calc(100vw - 100%); }（.container是所有内容的大容器）（IE9+  100vw：浏览器宽度；	100%：可用内容宽度）
各种BFC属性的特性与表现：
	overflow: hidden;	自适应，但“溢出不可见”限制应用场景
	float + float		包裹性 + 破坏性，无法自适应，块状浮动布局
	position: absolute	脱离文档流，自娱自乐
	display: inline-block	包裹性，无法自适应; IE6/7下，block水平无法识别
	display: table-cell	包裹性，但天生无溢出特性，绝对宽度也能自适应
overflow与绝对定位：
	overflow: hidden; 隐藏失效：元素设置了 position: absolute;
	overflow: auto; 滚动失效：元素设置了 position: absolute;
依赖于overflow的样式表现
	resize: both/horizontal/vertical;（此声明起作用的前提：元素的overflow属性值不能是visible）
		resize拖拽区域的大小是 17px * 17px （也就是滚动条的尺寸）
	text-overflow: ellipsis; ellipsis文字溢出...省略（此声明起作用的前提：元素设置了overflow:hidden;）
#   overflow-x:
如果overflow-x与overflow-y的值相同，则两者加起来等同于overflow
如果它们的值不相同，要是其中一个被设置成hidden或scroll或auto，另外一个被设置为visible，则visible会被重置为auto
#   overflow-y:
（请参考overflow-x）
#   clip:
！！！注意：该属性已被废弃，请用 clip-path 代替。
rect————用法：rect(top, right, bottom, left)   （在ie4-7中，这4个值之间是没有逗号的）
        top跟bottom均代表距离元素顶部边沿一定大小的位置，left跟right则代表距离元素左边边沿一定大小的位置。
        当rect()中的bottom值小于top值，或者right值小于left值时，整个剪切区域不会显示。
        top和left取值为auto，当top或者left取值为auto时，相当于取值为0；
        bottom和right取值为auto，当bottom和right取值为auto时，相当于元素的100%宽度。
        bottom和right取值为auto，当bottom和right取值为auto时，相当于元素的100%宽度。
        rect()不能支持百分比值。
auto————默认值。不应用任何剪裁。
inherit————规定应该从父元素继承 clip 属性的值。
clip属性只能在元素设置了“position:absolute”或者“position:fixed”属性起作用。
#   clear:
none————默认值。允许两边都可以有浮动对象
left————左侧抗浮动
right————右侧抗浮动
both————两侧抗浮动
清除浮动通用CSS：
    .fix { *zoom: 1; }
    .fix:after { content: ''; display: table; clear: both; }
clear使用原则：凡是clear:left或者clear:right起作用的地方，一定可以使用clear:both替换！
    原因在于，clear属性是让自身不能和前面的浮动元素（即在DOM的前面）相邻，注意这里“前面的”3个字，而float属性要么就left要么就right，不可能同时存在。
    由于clear属性对“后面的”浮动元素（处于该clear元素的DOM的后面）不闻不问，因此，当clear:left有效的时候，clear:right必定无效，也就是此时clear:left等同于设置clear:both。
    反之亦然。
关于clear重复声明：后面的声明会覆盖掉前面的声明。
#   font:
字体：字体样式 字体异体 字体粗细 字体大小/行高 字体系列；
font: italic bold 12px/20px arial,sans-serif;
其中，字体异体被忽略了，另外多个字体系列用逗号隔开。
font简写属性可设置的属性包括
    font-style
    font-variant
    font-weight
    font-size/line-height
    font-family
可以不设置其中的某个值，未设置的属性会使用其默认值。但是，至少要指定字体大小和字体系列。而且，顺序不能更改。
其中，
font-style负责设置字体的风格，默认是normal，可以另外设置italic(斜体)或oblique(倾斜)或inherit。
font-variant负责设置小型大写字母的字体显示文本(即把小写字母转换为大写的，但其字体变小)，默认为normal，可另设置small-caps或inherit。
font-weight负责设置文本的粗细，可设置的值有normal、bold、bolder、lighter、100-900、inherit。
除了组合各个属性，font还可以直接使用与用户计算机环境某个方面一致的字体，可设置的关键词如下
    caption			被标题控件（比如按钮、下拉列表等）使用的字体
    icon			被图标标记使用的字体
    menu			被下拉列表使用的字体
    message-box		被对话框使用的字体
    small-caption	caption 字体的小型版本
    status-bar		被窗口状态栏使用的字体
使用IOS、Android的默认字体（包括了英文和中文字体）：
    body {
        font: menu;
    }
    body {
        font: small-caption;
    }
    body {
        font: status-bar;
    }
使用关键字属性会不止设置字体，还有font-style、font-size等的值也会一并设置
#   font-family:
font-family 可以把多个字体名称作为一个“回退”系统来保存。如果浏览器不支持第一个字体，则会尝试下一个。也就是说，font-family 属性的值是用于某个元素的字体族名称或/及类族名称的一个优先表。浏览器会使用它可识别的第一个值。
可以指定的系列名称：具体字体的名称，比如："times"、"courier"、"arial"。
可以指定通常字体系列名称：比如："serif"、"sans-serif"、"cursive"、"fantasy"、"monospace"。
#   font-size:
属性设置元素的字体大小。注意，实际上它设置的是字体中字符框的高度；实际的字符字形可能比这些框高或矮（通常会矮）。
xx-small————
x-small————
small————
medium————（默认值）
large————
x-large————
xx-large————把字体的尺寸设置为不同的尺寸，从 xx-small 到 xx-large。
smaller————把 font-size 设置为比父元素更小的尺寸。
larger————把 font-size 设置为比父元素更大的尺寸。
length————把 font-size 设置为一个固定的值。其中包括了以下单位：
    px：绝对 1“视像素” 
    pt：绝对 1pt就是1/72英寸
    pc：绝对 1pc相当于12pt 
    em：相对 相对父元素的字体大小 
    rem：相对 （root em）相对于HTML字体大小 
    vw：相对 1/100的视口的宽度 
    vh：相对 1/100的视口的高度 
    vmin：相对 1/100的视口的小尺寸（高度或宽度）
    vmax：相对 1/100的视口的大尺寸（高度或宽度）
%————把 font-size 设置为基于父元素的一个百分比值。
inherit————规定应该从父元素继承字体尺寸。
#   font-style:
设置字体的倾斜样式。
normal————默认值。浏览器显示一个标准的字体样式。
italic————浏览器会显示一个斜体的字体样式。（效果比较粗糙）
oblique————浏览器会显示一个倾斜的字体样式。（效果比较顺滑）
#   font-weight:
设置字体的粗细。
normal————默认值。定义标准的字符。
bold————定义粗体字符。
bolder————定义更粗的字符。
lighter————定义更细的字符。
100~900————400时代表normal，700开始代表粗体。
inherit————规定应该从父元素继承字体的粗细。
#   src:
该属性是为了指定 @font-face 的字体数据源。（可用逗号间隔，同时指定多个值）
url()————指定字体文件的相对路径或网络绝对路径。（路径可用引号包含起来）
local()————指定一个在本地安装了的字体名称、字族名称。（字体名称、字族名称可用引号包含起来）
#   line-height:
line-height，行高，两行文字基线之间的距离。
    基线（Base line），指的是一行字横排时下沿的基础线，基线并不是汉字的下端沿，而是英文字母x的下端沿，同时还有文字的顶线（Top line）、中线（Middle line）和底线（Bottom line），用以确定文字行的位置
    顶线，就是汉字的上端沿。
    底线，就是汉字的下端沿。
    中线，就是汉字所在的垂直高度的中心水平线。（基线通常距离中线有一定的距离）
行高与字体尺寸的差称为行距（leading）。（说白了就是该行文字的顶线与上一行问题的底线的距离）
每一行中的每个元素都有一个内容区域，它是由那个行内元素的字体尺寸决定的。（查看方式：选中一段文字时所看见的背景颜色区域便是该段文字的内容区域）
行内元素会生成一个行内框（inline box），在没有其他因素影响的时候，行内框 等于内容区域，而设定行高则可以增加或者减少行内框的高度。
由于行高可以应用在任何元素上，因此同一行内的若干元素可能有不同的行高和行内框高。
行框（line box）。同行内框类似，行框是指本行的一个虚拟的矩形框，其高度等于本行内所有元素中行高最大的值。因此，当有多行内容时，每行都会有自己的行框。
    注意：行框的高度只同本行内元素的行高有关，而和父元素的高度（height）无关。
以em、ex和百分比为单位的行高，其基数是元素本身的字体尺寸。（行高可以设定得比字体高度小，此时多行的文字将叠加到一起）
行高默认是可继承的，但是继承的是计算值（例如父节点指定了font-size为20px，line-height为2em。而子节点只声明了font-size位30px，那么最终父元素所在行的行高为40px。因为子元素直接继承了40px的行高，而不是2em。）
    为了避免这种情况，可以定义一个没有单位的实数值作为缩放因子来统一控制行高，缩放因子是直接继承的，而不是继承计算值。（那么上面的例子中，子元素的行高就变成了60px，最终父元素所在行的行高就为60px。）
当内容中含有图片的时候，如果图片的高度大于行高，则含有图片行的行框将被撑开到图片的高度。（图片虽然撑开了行框，但是不会影响行高，因此也不会影响到基于行高来计算的其他属性。）另外，图片与文字默认为基线对齐。
normal————默认行高，一般为1到1.2；
实数————实数值，缩放因子；
长度————合法的长度值，可为负数；
百分比————百分比取值基于本元素的字体尺寸。
#   letter-spacing:
指定了字符之间的间距。（字符可以是字母、数字、汉字、空格等）
该属性还可以用于 ::first-line 以及 ::first-letter 伪类
normal————默认值。定义标准的字符间距。（在此属性的作用下，用户可通过文本对齐属性(text-align:justify;)来改变字符间距）
length————任意合法单位的长度值，甚至是负值。（但不支持百分比值或缩放因子）
          负值可能导致字符重叠在一起(-1em)或文本反向(-2em)。
          文本反向：文本的第一个字符位置不变，是后续字符的发展方向相反。
          要注意的是，长度值 0 和 normal 是不一样的。
#   word-spacing:
指定了单词之间的间距。（以空格为界，一个空格的两边通常算是两个单词，如果是中文字符组成的话就叫词组）
normal————默认值。定义标准的单词间距。
length————任意合法单位的长度值，甚至是负值。（支持百分比值，但不支持缩放因子）
          负值可能导致单词重叠在一起或文本反向(很大的负值)。
          文本反向：文本的第一个单词位置不变，是后续单词的第一个字符的位置发生变化。
          要注意的是，长度值 0 和 normal 是不一样的。
#   color:
color属性设置了一个元素的前景色（在 HTML 表现中，就是元素文本的颜色）。这个颜色还会应用到元素的所有边框，除非被 border-color 或另外某个边框颜色属性覆盖。（border-color等属性默认的值就是关键字 currentColor ）
color_name————各种关键词的颜色值在这：http://www.zhangxinxu.com/study/201008/css3-color-names.php
hex_number————规定颜色值为十六进制值的颜色（三个数分别代表红、绿、蓝颜色值），比如 #ff0000。（也可以使用简写 #f00 ）
rgb_number————规定颜色值为 rgb 代码的颜色，比如 rgb(255,0,0)。（里面的数值不能是小数，也不能是百分数和普通整数共同存在）
hsl_number————h表示Hue, 是色调的意思，取值懂0~360。
              s表示Saturation, 颜色饱和度的意思，0~100%表示，值越大，饱和度越高，颜色越亮。
              l表示Lightness，亮度的意思，也是0~100%表示，越亮。100%就是白色，50%则是正常亮度，0%的亮度就是黑色。
              例如：hsl(240,100%,50%)
raba_number————颜色支持Alpha透明通道。
hsla_number————颜色支持Alpha透明通道。
inherit————规定应该从父元素继承颜色。（IE不支持）
transparent————用来表示文字的颜色纯透明，transparent关键字可以近似认为是rgba(0,0,0,0)的缩写。（IE8以下不支持）
currentColor————指当前元素的文本的颜色。border、text-shadow、box-shadow等属性的默认颜色就是currentColor。
                凡是需要使用颜色值的地方，都可以使用currentColor替换，比方说背景色 – background-color, 渐变色 – gradient, SVG的填充色 – fill等等。
#   text-align:
text-align属性可以有效作用于inline/inline-block水平的元素。
start（实验性值）————当属性 direction 的值为 ltr（默认）时，start 等同于 left 。
         当属性 direction 的值为 rtl 时，start 等同于 right 。
end（实验性值）————当属性 direction 的值为 ltr（默认）时，end 等同于 right 。
       当属性 direction 的值为 rtl 时，end 等同于 left 。
left————以每一行的第一个inline节点的左边为限，行内的其他inline节点向左靠拢
right————以每一行的最后一个inline节点的右边为限，行内的其他inline节点向右靠拢
center————内容居中对齐。
justify————内容两端对齐。
           起作用的前提是该行不是最后一行（注意，这里的多行指的是正常的 inline/inline-block 节点流所形成的多行，通过 < br/> 断行的前面的部分只能算最后一行了）
           另外，这里可能涉及 inline-block 化。考虑到低版本IE，比较的实践是把 inline 标签 inline-block 化，而非把 block 标签 inline-block 化。
（还有其他几个实验性的值，暂不管。）
#   text-decoration:
text-decoration是支持多值的。
underline————为文本添加下划线。
             如果觉得下划线离文本太近，可用 border-bottom 来模拟下划线，通过 padding-bottom 来控制文字与下划线的距离。此方法的好处是我们可以利用 border-style 来得到不同的下划线哦。
             当然，border-bottom 会影响元素的大小（高度），从而可能影响布局。因此我们还可以通过 box-shadow 来模拟这个下划线。（IE9以上支持，这是不足）
overline————为文本添加上划线。（好像没什么卵用）
line-through————中划线，线条从文字的中间高度处穿过。（我通常都是用 del 标签）
blink————闪烁。根本没有浏览器支持。(`_')
none————在普通标签（非 a ）中为默认。
#   text-indent:
每一段的第一行的文本缩进。
length————任意合法单位的长度值，甚至是负值。
percentage————父容器的宽度的百分比值。
#   text-overflow:
起作用的前提：块级元素设置了 overflow 为 hidden，而且 white-space 为 nowrap 。（因为只有文本不会换行时，才有文本溢出的概念。在 overflow 为 visible 的情况下，text-overflow 是没意义的）
clip————修剪。（  ）
ellipsis————省略。（ ... ）
#   text-rendering:
这是一个 SVG 的相关属性。（一般情况不建议使用）
auto————浏览器将根据情况来优化文本速度、可读性、精度。实际中，Gecko内核浏览器比如火狐下如果字体大小是20px或者更大，将采用 optimizelLegibility 属性，否则使用 optimizeSpeed 属性。
optimizeSpeed————Gecko内核的浏览器将强调可读性和几何精度，同时绘制文本渲染速度，禁用字距和连写。
optimizeLegibility————Gecko内核的浏览器将强调可读性和几何精度，同时绘制文本渲染速度，启用字距和连写。
geometricPrecision————目前这个属性的意义和 optimizelegibility 一样
#   text-shadow:
CSS3的属性，可以指定多个值（通过逗号隔开），第一个叠在最上边。声明方式如下：
offset-x offset-y blur-radius color————x轴方向的偏移、y轴上的偏移、模糊半径（如果不指定，则默认为0）、颜色值（如果不指定，则默认用currentColor）
color offset-x offset-y blur-radius————颜色值（如果不指定，则默认用currentColor）、x轴方向的偏移、y轴上的偏移、模糊半径（如果不指定，则默认为0）
注意：上面所说的模糊半径为0并不是说投影消失了，只是投影不再四周扩散了而已。
#   text-transform:
该属性是为了控制文本的大小写。类字母字符（即会分大小写）有效，像中文这种象形文字就无效。
none————默认。定义带有小写字母和大写字母的标准的文本。
capitalize————文本中的每个单词以大写字母开头。
uppercase————文本全是大写字母。
lowercase————文本全无大写字母，仅有小写字母。
inherit————规定应该从父元素继承 text-transform 属性的值。（IE8以下不支持）
#   word-break:
normal————自然断开。中文换行，英文不断词（当单词的长度超过该行剩余的长度时，单词会移到下一行。当英文单词长度超过一行时会导致溢出容器）。
break-all————可以从任意地方断开，包括标点符号不能做行首等全部无效。（所有浏览器支持）
keep-all————中文不换行，英文单词不断词。（移动端支持有限）
#   word-wrap:
CSS3中，已经把 word-wrap 改名为 overflow-wrap 。（但 overflow-wrap 的支持仍相当有限，因此，从兼容性的角度来说，还是用 word-wrap 比较好）
normal————自然断开。中文换行，英文不断词（当单词的长度超过该行剩余的长度时，单词会移到下一行。当英文单词长度超过一行时会导致溢出容器）。
break-word————如果这一行文字有可以换行的点，如空格，或CJK(Chinese/Japanese/Korean)(中文/日文/韩文)之类的，则就不打英文单词或字符的主意了，让这些换行点换行。
              即比剩下的空间长一点的单词会移到下一行。如果一个单词超过了一行，那这个单词最终还是会被断词的。（即该值与 normal 的唯一区别就是是否将长于一行的单词进行断词处理）
#   white-space:
属性的作用是指定空白字符（换行、缩进、空格）如何被处理。
normal————所有连续的空白字符将塌陷成为一个空格。字符将在容器的末尾进行换行
nowrap————所有连续的空白字符将塌陷成为一个空格。所有字符不会换行直到遇到 < br> 标签。
pre————所有的空白字符将被保留，但字符不会换行，直到遇到 < br> 标签或换行符。（也就是说，一段的内容将在一行上展示）
pre-wrap————所有的空白字符将被保留，字符在到达容器末尾将正常进行换行。（当然，遇到 < br> 标签或换行符也会进行正常的换行）
pre-line————所有的空白字符将被保留，除非空白字符到达了容器的（该行的）末尾。（每行末尾的空白字符将被删去）
#   vertical-align:
vertical-align支持的属性以及组成：
	1、线类：baseline、top、middle、bottom
	2、文本类：text-top、text-bottom
	3、上标下标类：sub、super
	4、数值百分比类：20px、2em、20% ……
		共性：都带数字、都支持负值、行为表现一致（在baseline对齐基础上上下偏移对应数值大小）
		差异：vertical-align的百分比值是相对于line-height计算的（IE6/7下vertical-align百分比值不支持小数line-height）
vertical-align起作用的前提：
    只能应用于 inline水平 以及 'table-cell' 元素（默认状态下，也即 图片、按钮、文字、单元格 支持vertical-align）
	inline水平：
		inline：< img>、< span>、< strong>、< em>、未知元素 ...
		inline-block：< input>(IE8+)、< button>(IE8+) ...
	'table-cell' 元素：
		table-cell：< td>
display：能更改元素的显示水平
	例如把一张图片设置为 display: block; 后，vertical-align即失效
某些CSS声明：能间接更改元素的显示水平
	例如把一张图片设置为 float: left; 或 position: absolute; 后，会使图片block水平化，从而vertical-align失效
使图片在父级(block水平)元素中垂直居中：
	1、将父级元素的 line-height 设置为父级元素的高度大小，然后再为图片设置 vertical-align: middle; 即可
	2、对父级元素设置 display: table-cell; vertical-align: middle; 即可（起作用的是table-cell本身）
实现多行文字与图片的垂直居中：
	包裹文本的元素设置 display: inline-block; vertical-align: middle; 图片设置 vertical-align: middle;
对于内联元素，vertical-align与line-height虽然看不见，但实际上到处都是！（一对好基友）
如何去掉图片与容器的底部间隔：
	1、图片block水平化（ 使vertical-align失效 ）
	2、改变图片的默认对齐方式（ 对图片设置vertical-align: bottom/middle/top; ）
	3、改变容器的行高（ 设置line-height: 0; ）
	4、改变容器的字体大小（ 设置font-size: 0; 即间接改变容器的行高 ）
实现图片相对于容器的近似居中：
	容器的line-height设置为容器的高度（比图片的高度值要大），图片设置 vertical-align: middle; 即可
使一个空的兄弟内联结点不撑开图片与容器底部的距离：
	对容器设置：line-height: 0; 对空的兄弟元素设置：vertical-align: top;
当line-height为0时，文字与容器的位置关系：
	1、行高为0，则文字字符占据容器的高度也就变为0了
	2、行高是决定文字的中心的，因此文字的高度也就移到了文字的中心
	3、文字的高度就是它在容器的位置，因此文字的高度会出现在容器的顶部（为0了嘛）
	4、此时，基线继续在文字的底部（inline-block元素默认的是基线对齐哦）
inline-block水平元素的默认基线位置：
	1、当元素完全没有内容时，它的基线是容器的底部边沿
	2、它的基线是里面的 inline box 的最后一行的基线
为inline-block水平的空的 span 为什么撑开了一段高度？
	原因：与span在同一行的空白字符(摸不着的)的高度为0，但由于字体大小的原因，该空白字符的基线（字体底部）离字符中心为1/2字体大小的高度，
	      而span为空元素
因此必须与该空白字符基线对齐，从而把容器的底部撑开了1/2字体大小的高度
为inline-block水平的非空的 span 为什么不撑开高度了？
	原因：该span的基线在拥有内容后不再是底部边沿，而是与 line box 的基线一致了，由于其高度为0（因为line-height为0），line-height
vertical-align: bottom; 的作用：
	在inline/inline-block水平元素中：使当前元素与整行 inline box 的底部对齐（inline box的其他内容则是baseline对齐）
	在table-cell元素中：单元格底padding边缘和表格行的底部对齐
vertical-align: top; 的作用：
	与vertical-align: bottom; 的作用刚好相对
vertical-align: middle; 的作用：
	1、inline/inline-block元素：元素的垂直中心点和父元素基线上1/2的 字符的高度 处对齐
	2、table-cell元素：单元格填充盒子相对于外面的表格行居中对齐(td单元格不足高度会用padding填补)
如何利用vertical-align实现图片的完全的垂直居中：
	容器设置 line-height: 某个大于图片高度的值; font-size: 0; 图片设置：vertical-align:middle;
vertical-align: text-top;
	inline盒子的顶部和父级 content area 的顶部对齐。（一定要注意：是父级的font-size的大小的content area区域！）
vertical-align: text-bottom;
	inline盒子的底部和父级 content area 的底部对齐。（与行高没有任何关系，只与父级的font-size有关）
text-top、text-bottom的作用：
	用于定位固定大小的图标，以避免其受到行高或其他内联元素的影响
vertical-align: super
	提高盒子(本内联盒子)的基线到父级合适的上标基线位置
vertical-align: sub
	降低盒子的基线到父级合适的下标基线位置
相邻元素不同的vertical-align的行为表现：
	关于 top 和 bottom：	
		对方可能受到高度最大的元素的影响，但并没有直接的影响，你对齐底部，我对齐顶部，互不干扰，没有关联
	关于 text-top 和 text-bottom：
		对方受到父级元素font-size大小的影响，相互之间并没有关联，请参照 vertical-align: text-top/text-bottom; 的讲解
如何使带有文字内容的容器的图片完全垂直居中：
	把文字放置到一个span标签中，img 和 span 都设置 vertical-align: middle; 而父元素设置一个大于图片高度的line-height即可
text-bottom与baseline：
	一个inline元素设置了 vertical-align: text-bottom; 后，它所对齐的content-area的底部是inline-box的content-area的底部
	不要被另外设置了 vertical-align 的其他的inline元素影响了你对第一个inline元素的位置的判断！因为inline-box可能暂时是空的
	但其所占的空间确实存在！
vertical-align到底如何影响元素：
	切记，它只与当前元素和父级元素有关。与前后其他内联元素无任何关系！（不要被元素的相邻元素干扰对vertical-align的理解）
实现小图标与文字的居中对齐：
	为小图标设置一个合适的 vertical-align 负值即可（兼容性较好）
如何实现一张图片自适应垂直居中
	< p>< img src="a.jpg"/>< i></ i></ p>
	html,body{ height: 100%; }
	p{ height: 100%; }
	img{ vertical-align: middle; }
	i{ display: inline-block; height: 100%; vertical-align: middle; }
如何实现多行文字自适应垂直居中
	< p>< span>很多标签或文字内容</ span>< i></ i></ p>
	html,body{ height: 100%; }
	p{ height: 100%; }
	span{ display: inline-block; vertical-align: middle; }
	i{ display: inline-block; height: 100%; vertical-align: middle; }
#   list-style:
该属性作用于 li 元素或 display 为 list-item 的元素，可通过继承而得，因此常常被设置于 ol 或 ul 上。
该属性是 list-style-type、list-style-position 和 list-style-image 的简写，默认值为：disc outside none
值的个数可以是一、二、三个，值的位置可调换。
#   list-style-type:
类型图标的颜色和元素定义的 color 一致。兼容性比较好的值包括：
none————没有类型图标
disc————实心小圆圈
circle————空心小圆圈
square————实心小方块
decimal————十进制数字 1 2 3 4 （默认）
lower-alpha————大写字母 a b c d
upper-alpha————大写字母 A B C D
lower-roman————小写罗马字符 i ii iii iv
upper-roman————大写罗马字符 I II III IV
lower-latin————小写拉丁文 a b c d
upper-latin————大写拉丁文 A B C D
lower-greek————小写希腊文 α β γ δ
armenian————亚美尼亚文 Ա Բ Գ Դ
georgian————格鲁吉亚文 ა ბ გ დ
decimal-leading-zero————带有前导0的十进制数字 01 02 03 04
#   list-style-position:
inside————类型图标（或类型图片）将会在 li 元素里面显示，li 内部的内容将进行相应的左移。
outside————类型图标（或类型图片）将会在 li 元素外显示。当然，图标还是在 ul 或 ol 内部。
inherit————从父结点（ul、ol、包含display为list-item的结点的父元素）继承。（默认值）
#   list-style-image:
none————没有类型图片。
url('...')————指定类型图片的路径。
inherit————从父结点（ul、ol、包含display为list-item的结点的父元素）继承。（默认值）
#   pointer-events:
auto————跟不设置值一样。在SVG中，该值与 visiblePainted 的作用相同。
none————元素不响应一切的鼠标、触摸事件。
        注意，该元素的子元素设置了另外的值，则子元素还是可以响应鼠标、触摸事件的，通过事件捕获或冒泡还是可以触发元素（值为none父元素）的相应的事件监听器。
        利用 a 标签，不要设置href，再加上 pointer-events 为 none 就可以达到禁用按钮或链接的效果（pointer-events为none是为了去除鼠标事件，无href则是为了避免键盘响应）
visiblePainted————该值只支持SVG。元素只有在以下情况才会成为鼠标事件的目标：
                  1、visibility属性值为visible，且鼠标指针在元素内部，且fill属性指定了none之外的值
                  2、visibility属性值为visible，鼠标指针在元素边界上，且stroke属性指定了none之外的值
visibleFill————该值只支持SVG。只有在元素visibility属性值为visible，且鼠标指针在元素内部时,元素才会成为鼠标事件的目标，fill属性的值不影响事件处理。
visibleStroke————该值只支持SVG。只有在元素visibility属性值为visible，且鼠标指针在元素边界时,元素才会成为鼠标事件的目标，stroke属性的值不影响事件处理。
visible————该值只支持SVG。只有在元素visibility属性值为visible，且鼠标指针在元素内部或边界时,元素才会成为鼠标事件的目标，fill和stroke属性的值不影响事件处理。
painted————该值只支持SVG。元素只有在以下情况才会成为鼠标事件的目标：
           1、鼠标指针在元素内部，且fill属性指定了none之外的值
           2、鼠标指针在元素边界上，且stroke属性指定了none之外的值
           visibility属性的值不影响事件处理。
fill————该值只支持SVG。只有鼠标指针在元素内部时,元素才会成为鼠标事件的目标，fill和visibility属性的值不影响事件处理。
stroke————该值只支持SVG。只有鼠标指针在元素边界上时,元素才会成为鼠标事件的目标，stroke和visibility属性的值不影响事件处理。
all————该值只支持SVG。只有鼠标指针在元素内部或边界时,元素才会成为鼠标事件的目标，fill、stroke和visibility属性的值不影响事件处理。
#   cursor:
以下各种指针效果请参考：https://developer.mozilla.org/en-US/docs/Web/CSS/cursor
url('...') x y————以特定的图片作为鼠标指针。（x, y）为可选值，指定图片相对于左上角参考点进行定位，这两个值必须非负而且需小于32。
auto————交由浏览器决定
default————默认的鼠标大箭头
none————没有鼠标指针
context-menu————带有菜单标志的大箭头。在现代浏览器中与 default 一致。
help————带有问号的大箭头
pointer————按下动作的小手
progress————带有等待标志的大箭头
wait————等待标志
cell————类似于Excel的单元格指针
crosshair————十字
text————水平文本标志
vertical-text————垂直文本标志
alias————带有快捷标志的大箭头
copy————带有拷贝标志的大箭头
move————拖动标志
no-drop————带有禁止标志的按下动作的小手
not-allowed————禁止标志
e-resize————向东（右）的小箭头。在现代浏览器中与 ew-resize 一致。
n-resize————向北（上）的小箭头。在现代浏览器中与 ns-resize 一致。
ne-resize————向东北（右上）的小箭头。在现代浏览器中与 nesw-resize 一致。
nw-resize————向西北（左上）的小箭头。在现代浏览器中与 nwse-resize 一致。
s-resize————向南（下）的小箭头。在现代浏览器中与 ns-resize 一致。
se-resize————向东南（右下）的小箭头。在现代浏览器中与 nwse-resize 一致。
sw-resize————向西南（左下）的小箭头。在现代浏览器中与 nesw-resize 一致。
w-resize————向西（左）的小箭头。在现代浏览器中与 ew-resize 一致。
ew-resize————东西（左右）双向小箭头
ns-resize————南北（上下）双向小箭头
nesw-resize————东北与西南（左上与右下）双向小箭头
nwse-resize————西北与东南（右上与左下）双向小箭头
col-resize————列宽大小调整标志
row-resize————行高大小调整标志
all-scroll————全方位滚动标志。在现代浏览器中与 move 一致。
zoom-in————放大标志（CSS3属性，现代浏览器才支持）
zoom-out————缩小标志（CSS3属性，现代浏览器才支持）
grab————手掌伸开标志（CSS3属性，现代浏览器才支持）
grabbing————手掌抓住标志（CSS3属性，现代浏览器才支持）
#   background:
背景：颜色值 图片url地址 背景图片重复模式 背景图片滚动模式 背景图片位置；
在这里颜色值就是该元素的背景颜色，背景图片则是不重复的、不随着鼠标滚动的，且图片所在的位置是元素的所呈现的范围的中心（包括宽高）；
background: #f00 url(img/01.jpg) no-repeat fixed center;
background简写属性可设置的属性包括
    background-color
    background-position
    background-size		（css3）
    background-repeat
    background-origin	（css3）
    background-clip		（css3）
    background-attachment
    background-image
其中，
background-position负责设置背景图片的方位，默认在左上角；如果仅设置一个值(left/right/top/bottom)，那么第二个值默认为center。
background-size负责设置背景图片的尺寸，可以设置为cover(完全覆盖背景区域)、contain(图片的宽高比不变的情况下，最大地适应内容区域)
    [length/percentage](第一个值设置宽度，第二个值设置高度，若只设置第一个值，第二个默认为auto)，其中percentage是根据父元素
    的百分比来进行计算。（background-position-x:0%;是左边从往右边算，background-position-x:100%;是从右边往左边算！）
background-origin负责设置背景图片的相对定位点(均为左上角)，默认的padding-box，可以另外设置border-box或content-box。
background-clip负责设置背景(包括图片和颜色)被裁剪的位置，默认是border-box，可以另外设置padding-box或content-box。
background-attachment负责设置背景图片对屏幕滚动事件的响应，默认是scroll，可以另外设置fixed或inherit。
#   background-attachment:
scroll————背景图片参照元素本身而固定，而不是随着内容的滚动而滚动（但会随着元素的滚动而滚动）
fixed————背景图片参照整个屏幕而固定，不会随着视窗的滚动而滚动（包括元素的滚动和内容的滚动）
local————背景图片参照元素中的内容而固定，会随着元素内部内容的滚动而滚动
#   background-color:
transparent————默认值。
值的类型请参考 color 。
#   background-image:
复习一下7阶层叠水平(stacking level)：
	background/border < 负z-index < block块状水平盒子 < float浮动盒子 < inline/inline-block水平盒子 < z-index:auto或看成z-index:0 < 正z-index
    另外， border 在 background-image 的层级上面， background-color 在 background-image 的层级下面。
而 background-image 的定位是由 background-origin 决定的。background-image 的能到达的边界是由 background-clip 决定的。
如果所设置的背景图片无效，那么该值将被当成 none 来处理。
background-image 和 background-color 可以分别设置，互不影响。但 background 与 background-image、background-color 冲突，以“后定义者”为准。
    非常重要的一点是，设置 background 会直接把前面的所有与 background-image 相关的属性重置掉（使其无效）。当然，前面设置的 background-color 也会被重置。
在CSS3中，background-image 支持多值。
#   background-position:
该属性是用于定位背景图片的位置，对背景颜色无效。第一个值决定背景图片的水平位置，第二个值决定图片的垂直位置。
在CSS2.1中，值的个数为1个或2个：
length————如果只设置了一个值，相当于（npx 50%）。再例如双值： 10px 20px 。即背景位于 box-sizing 的左上角 10px 20px 处。
percentage————如果只设置了一个值，相当于（n% 50%）。另，0% 0% 是该属性的默认值。
在CSS3中，值的个数在CSS2.1的基础上，可以分别为水平位置或垂直位置设置起始点（left/right、top/bottom）。即定位的参考点变成了四个角中的一个：
完整的例子：
right 10px bottom 20px————背景图片距离元素的 box-sizing 右边10px，距离元素的 box-sizing 下边20px。
单值的情况：
left————相当于 left center 。（0% 50%)
center————相当于 center center 。（50% 50%) 。此时，背景图片刚好居于元素的水平垂直中心。
right————相当于 right center 。(100% 50%)
top————相当于 center top 。(0% 50%)
bottom————相当于 center bottom 。(50% 100%)
即，如果仅设置一个值( left/right/top/bottom 或其他数值 )，那么第二个值默认为center。
可设置负值。
background-position默认是相对左上方定位的！
    而且，是相对于 padding-box 的左上角进行定位的。
拓展：CSS中的盒模型 box-sizing ，分为 content-box padding-box border-box （margin-box不被支持）
background-position的100%(右侧)定位不计算border区域（ 只计算内容和两侧padding区域，因为box-sizing默认为padding-box ）。
    {border-right:50px solid transparent; background-position: 100% 40px;}  可实现背景图片相对于容器的右边50px、顶部40px定位
#   background-repeat:
在CSS2.1中，
repeat————朝着x、y轴进行平铺（默认值）
repeat-x————只朝着x轴进行平铺
repeat-y————只朝着y轴进行平铺
no-repeat————不进行平铺
在CSS3中，
用 repeat repeat 代替 repeat 。（当然，只写一个 repeat/no-repeat 则会被解析成两个，保证了向后兼容）
space————（ 相当于 space space ）平铺的背景图片在 box-sizing 中两端对齐，其多出来的空间成为背景图片之间的空隙，但元素两端与背景图片没有空隙。
         （背景图片不会扭曲）
round————（ 相当于 round round ）平铺的背景图片在 box-sizing 中两端对齐，但其多出来的空间通过自身的拉伸来填充。
         （容易导致背景图片扭曲）
#   background-size:
CSS3新增属性（IE9+支持）
在CSS2.1中，我们是没有办法控制背景图片的大小的。
默认值为 auto auto
cover————将背景图片在元素的 x 和 y 方向均100%拉伸，同时保持图片的宽高比不变。（超出元素的部分自动被截除）
contain————在保证图片的宽高比的前提下，将背景图片尽可能地放大。（ x 方向为100%，或 y 方向为100%）
percentage————百分比值是根据背景图片所在的元素的 box-sizing（默认是 padding-box ）的大小进行计算的。不能是负值。如果只设置一个值，则 height 为 auto。
length————任意合法单位的长度值，不能是负值。
background-size支持多值，用逗号隔开每张 background-image 的 background-size 。
#   content:
该属性主要结合 :before 和 :after 伪元素生成内容（IE8以上支持）
none————伪类元素没有任何填充。
normal————与值 none 一样。
< string>————伪元素填充如'XX'这些字符串。
< uri> | url()————伪元素用外部资源如图片填充。如果该资源(图片)失效，那么它会被忽略或显示一些占位符。
counter( name [, style] )————此方法用于输出计数源的值，主要用在 content 属性内。style的参数值可以是 list-style-type 支持的那些值。
counters( name, separator )————此方法用于输出带有子序号的前缀。使用方法与 counter() 基本一致。
attr(X)————返回DOM元素上的属性值（如src）。如果该属性不存在，则返回一个空字符串。（属性名是否大小写敏感则和DOCTYPE有关）
open-quote | close-quote————开引号、闭引号。引号类型由 quotes 决定。
no-open-quote | no-close-quote————无开引号、无闭引号
应用：
:after + content 清除浮动
    .fix:after{display:block; content:"clear"; height:0; clear:both; overflow:hidden; visibility:hidden;}
:after + content 实现图片垂直居中
    .pic_box{font-size:0; *font-size:200px;}    //*font-size是为了兼容ie7，设大一点的字体，IE7就可以实现图片垂直对齐
    .pic_box img{vertical-align:middle;}
    .pic_box:after{display:inline-block; width:0; height:100%; content:"center"; vertical-align:middle; overflow:hidden;}
    瑕疵：如果还需要水平居中图片，Chrome浏览器的水平居中貌似左边偏移了点，这是因为Chrome浏览器font-size:0，不能消除空格产生的水平距离的原因。
#   quotes:
该属性指定了客户端(浏览器)的嵌套引用标签的引号类型。
（q、blockquote标签的内容会被自动添加引号，而quotes则可以决定引号的类型，就酱）
none————规定 "content" 属性的 "open-quote" 和 "close-quote" 的值不会产生任何引号。
[< string> < string>]+ ————定义要使用的引号。前两个值规定第一级引用嵌套，后两个值规定下一级引号嵌套，以此类推。
这些引号通常是：
 " ————双引号
 ' ————单引号
 ‹ ————单一的左尖括号
 › ————单一的右尖括号
 « ————双的左尖括号
 » ————双的右尖括号
 ' ————左引号(单 high-6)
 ' ————右引号(单 high-9)
 " ————左引号(双 high-6)
 " ————右引号(双 high-9)
 „ ————双引号(双 low-9)
#   outline:
值的设置方式跟 border 一致。使用方式请参考 border。
但 outline 和 border 又不一样。outline不占据任何空间；在层叠水平层级中，它们是位于内容的上方的（border则位于内容下方）。
能去掉 IE6/7 的链接虚框的IE私有属性为 hidefocus="true" 。（尽量别用，因为会让链接外框完全消失，还会屏蔽focus事件）
很多 css reset 文件的 :focus{outline:none;} 是不合理的。因为这对于键盘使用者而言，页面可用性大大降低了。
解决办法：将 :focus{outline:none;} 改成 :active{outline:none;} ，
    这样，既可以让鼠标使用者点击时去掉丑陋的外框，又保留了键盘使用者需要看到的焦点外框。
现在除了Firefox，其他浏览器均还不支持 outline-radius 。
解决办法：用 box-shadow 模拟outline圆角
    .box{border-radius: 1px;box-shadow: 0 0 0 30px #cd0000;} ，然后在 .box 内放置所需的元素即可。
#   outline-offset:
该属性用于设置 outline 与 元素本身的边沿或border之间的空间大小，空间是透明的。（outline默认包裹着border）
length————任意合法单位的长度值，甚至是负值。（不能设置百分比）
#   opacity:
该属性指定一个元素（包括了其子元素）的透明度。
如果只想设置元素的部分内容的透明度或不影响子元素的透明度，就不能使用该属性，用 raba() 对那部分内容分别设置就好。
0~1————0至1之间的小数。0代表完全透明，1代表完全不透明。
低于IE9的IE浏览器， {opacity:0.3;} 的效果可以用 {filter: alpha(opacity=30);zoom: 1;} 来实现。
#   filter:
（该属性在 IE13+浏览器、Android4.4 下支持）
类似于PS中的滤镜，该属性的作用是为所有元素的 图片、背景、边框 等设置图像效果如 模糊、锐化、变色 等。
在CSS3中，该属性尚是一个试验性属性，如果考虑兼容性问题，可以用 svg 的 filter 属性替代。
在SVG中，该属性可应用于除< defs>元素外的所有内置元素。
值的类型：< filter-function> [< filter-function>]* | none    （即一个或多个功能函数，如果功能函数无效，则默认为none）
可应用的功能函数如下：
none————默认值。
url(resources.svg-url#element-id)————该函数指定一个设置了SVG滤镜的XML文件的路径，以及可能包含一个指定应用元素的锚点。
blur(5px)————为图片应用高斯模糊(参数指定屏幕上以多少像素融在一起，即标准差)，值越大，图片越模糊（不支持百分比值）。
brightness(0.5)————为图片应用线性乘法，使得图片变得更亮或更暗。如果值是0%，图像会全黑。值是100%，则图像无变化。
    其他的值对应线性乘数效果。值超过100%也是可以的，图像会比原来更亮。如果没有设定值，默认是1。
contrast(200%)————设置图片的对比度。默认值为1，取值范围为 0%-X%(X为任意非负数) 。值为0时，图片会变成纯灰色(不同颜色没有对比度)。
drop-shadow(16px 16px 10px black)————前两个参数分别代表x方向、y方向的偏移值(必须值)，而第三个值开始则是可选的。
    第三个参数指定模糊半径，第四个参数指定阴影的扩散半径(支持负值)，第五个参数则是阴影颜色。它跟 box-shadow 属性很像，
    但 filter 中的 drop-shadow 不能像 box-shadow 可以叠加阴影。（这两者中，后者的阴影距离更小、色值要更深，而且IE9+支持）。
    最重要的一点是，box-shadow只是元素盒子的阴影，而drop-shadow是真正的基于颜色的投影。（透明的地方不会出现投影）
grayscale(100%)————设置图片的灰度，参数100%代表完全转为灰度图片。0为默认值，代表图片灰度没发生任何变化。值的范围为 0%-100%。
hue-rotate(90deg)————为图片调整一个色相旋转值。默认值为0，值的范围为0deg-360deg。
invert(100%)————对图片进行反色处理(即取补色，反色与原色叠加就变成了纯白色)。默认值为0，取值范围为 0%-100% 。
opacity(50%)————对图片进行透明度处理。默认值为1，取值范围为 0%-100% 。可参考CSS属性 opacity 。
saturate(200%)————设置图片的饱和度。默认值为1，取值范围为 0%-X%(X为任意非负数) 。
sepia(100%)————设置图片的褐化值。默认值为0，值为100%则完全是深褐色的。值的范围为 0%-100% 。
#   visibility:
该属性的目的是为了让元素“隐藏”起来。
visible————默认值。元素可见。
hidden————元素不可见，但元素依然占据着文档空间。
collapse————当在表格元素中使用时，此值可删除一行或一列，但是它不会影响表格的布局。
    被行或列占据的空间会留给其他内容使用。(相当于 display:none; 但其他行与列的宽和高不会重新计算，
    行与列的宽高计算依然会将被设为 collapse 的行和列考虑进去。这是用于快速从表格中删除一行或一列，
    而无需重新计算表格其他元素的宽和高。)
    如果此值被用在其他的元素上，会呈现为 "hidden"。(相当于visibility:hidden;)
与其功能差不多的做法有：
display: none; 
    /* 不占据空间，无法点击，屏幕阅读器不可识别 */
visibility: hidden; 
    /* 占据空间，无法点击 */
position: absolute; clip:rect(1px 1px 1px 1px); 
    /* 不占据空间，无法点击 */
position: absolute; top: -999em; 
    /* 不占据空间，无法点击，屏幕阅读器可识别 */
position: relative; top: -999em; 
    /* 占据空间，无法点击 */
position: absolute; visibility: hidden; 
    /* 不占据空间，无法点击，屏幕阅读器不可识别 */
height: 0; overflow: hidden; 
    /* 不占据空间，无法点击 */
    失效情况：祖先元素没有position:relative/absolute/fixed声明，同时内部子元素应用了position:absolute/fixed声明。
    深层作用：解决标签内因打了个&nbsp;空格，而产生空白高度的问题。（由于line-height和font-size具有继承性，line-height:0;
        或 font-size:0; 都不是好方法。）。font-size还有Chrome默认文字无法小于12像素问题，考古版本IE下0像素文字呈现小点的问题。
opacity: 0; filter:Alpha(opacity=0); 
    /* 占据空间，可以点击 */
position: absolute; opacity: 0; filter:Alpha(opacity=0); 
    /* 不占据空间，可以点击 */
zoom: 0.001;-moz-transform: scale(0);-webkit-transform: scale(0);-o-transform: scale(0);transform: scale(0);
    /* IE6/IE7/IE9不占据空间，IE8/FireFox/Chrome/Opera占据空间。都无法点击 */
position: absolute;zoom: 0.001;-moz-transform: scale(0);-webkit-transform: scale(0);-o-transform: scale(0);transform: scale(0); 
    /* 不占据空间，无法点击 */
display:none;与visibility:hidden;的其他区别：
    1、 display:none隐藏产生reflow和repaint(回流与重绘)，而visibility:hidden没有这个影响前端性能的问题。
    2、 一旦父节点元素应用了display:none，父节点及其子孙节点元素全部不可见。
        通常情况下，我们给一个父元素应用visibility:hidden，则其子孙后代也都会全部不可见。
        如果子孙元素应用了visibility:visible，那么这个子孙元素又会重新地显现出来。
一个BUG：在低版本webkit内核中，绝对定位元素，其display值在inline/inline-block和block之间切换时候，是不重新渲染的。
    (IE7也不会换行，但那是解析bug。)
    解决方案：-webkit-transform: translateZ(0);（效果相当于老IE时代的 zoom:1; ）
另一个BUG：在低版本webkit内核中，绝对定位元素，同时visibility:hidden时候，如果子元素具有块状水平，同时设置了overflow:hidden; 
    则父元素hover时候，无法让子元素visibility:visible渲染生效！
    解决方案：-webkit-transform: translateZ(0);
注意，visibility支持transition过渡动画。
    visibility:hidden可以看成visibility:0;
    visibility:visible可以看成visibility:1;（实际上，只要visibility的值大于0就是显示的。）
    意义：让元素在动画结束后能自动隐藏！（因为display:none;无法应用transition效果）
    原理： 如果你只用透明度的话，那下面的元素将会被遮住，如果你用了visibility就不会挡住下面的元素，下面的元素仍然可以操作！
#   size:
（在input标签中，size属性的值指定了输入字段的宽度，即可见字符数，与maxlength不是同一个概念，建议用css的width替代）
CSS3实验性属性，慎用。
该属性的作用是定义展示页面的盒子的大小的方向。
使用方式：@page {size: 4in 6in landscape;}
auto————由用户端决定页面的大小。大多数情况下，使用的是靶纸(屏幕或打印机)的尺寸和方向。
landscape————页面的内容以风景(画)的方式呈现（盒子的最长边是水平的）
portrait————页面的内容以肖像(画)的方式呈现（这是默认的方向，盒子的最长边是垂直的）
< length>————任意合法单位的长度值。第一个值指定了页面盒子的宽度，第二个指定了高度。如果只设置了单值，那么宽和高都会应用该值。
A5————标准的 ISO 尺寸: 148mm x 210mm.
A4————标准的 ISO 尺寸: 210mm x 297mm. (个人打印中最常用的尺寸)
A3————标准的 ISO 尺寸: 297mm x 420mm.
B5————标准的 ISO 尺寸: 176mm x 250mm.
B4————标准的 ISO 尺寸: 250mm x 353mm.
JIS-B5————标准的 JIS 尺寸: 182mm x 257mm.
JIS-B4————标准的 JIS 尺寸: 257mm x 364mm.
letter————北美的信纸尺寸: 8.5in x 11in.
legal————北美的法文纸张尺寸: 8.5in x 14in.
ledger————北美的分类账纸尺寸: 11in x 17in.
#   zoom:
非标准属性，慎用。
该属性用于控制一个元素的有效缩放。
由于该属性非标准，而且影响元素的布局，建议用 transform: scale() 替代，
    当然，scale不支持百分比值但支持负值。
    另外，scale还可分别支持x/y两个维度的缩放。
zoom和scale的差别：
    zoom的缩放是相对于左上角的；而scale默认是居中缩放；
    zoom的缩放改变了元素占据的空间大小；而scale的缩放占据的原始尺寸不变，页面布局不会发生变化；
    zoom和scale对元素的渲染计算方法可能有差异。（使用zoom缩放的图片变得锐利，使用scale缩放的图片变得模糊）
    对文字的缩放规则不一致。zoom缩放依然受限于最小12像素中文大小限制；而scale就是纯粹的对图形进行比例控制，文字也会根据比例进行缩放。
    渲染的性能差异明显。在文档流中zoom加在任意一个元素上都会引起一整个页面的重新渲染；scale变化时，其原本的尺寸不变，因此没有layout的重计算。
需要注意的是：Chrome等浏览器下，zoom/scale不要同时使用，因为，缩放效果会累加。
normal————元素显示正常大小。默认值。 (1.0 = 100% = normal)
< percentage>————缩放因子。大于100%是放大，小于100%是缩小。（不能为负值）
< number>————缩放因子。大于1.0是放大，小于1.0是缩小。（不能为负值）
应用：
    清除IE6/7的浮动 .fix{*zoom:1;}
    原理：*zoom:1;可以给IE6/IE7浏览器增加haslayout, 用来清除浮动，修复一些布局上的疑难杂症等。
#   transform:
transform指变换，包括了拉伸、缩放、旋转、偏移。（还分为2D和3D）
同时有多个变换时，需要用空格隔开。
2D下，
拉伸：skew(35deg);     //相当于skew(35deg, 35deg);
      skewX(120deg);
      skewY(1.05rad);
缩放：scale(1, 0.5);
      scaleX(2);
      scaleY(0.5);
旋转：rotate(90deg);   //相当于rotate(0.25turn);
      rotateX(10deg);
      rotateY(10deg);
偏移：translate(10px, 20px);
      translateX(2em);
      translateY(3in);
矩阵：matrix(1.0, 2.0, 3.0, 4.0, 5.0, 6.0);
3D下，
缩放：scale3d(2.5, 1.2, 0.3);
      scaleZ(0.3);
旋转：rotate3d(1, 2.0, 3.0, 10deg);
      rotateZ(10deg);
偏移：translate3d(12px, 50%, 3em);
      translateZ(2px);
矩阵：matrix3d(1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1, 0, 0, 0, 0, 1);
视点：perspective(17px);
元素应用了该属性后的各种奇葩影响
    1、在Safari（包括iOS的Safari，iPhone上的微信浏览器，以及Mac OS X系统的Safari浏览器）中，3D变换会忽略z-index的层级。
       当我们使用3D transform变换的时候，如果祖先元素没有overflow:hidden/scroll/auto等限制，则会直接忽略自身和其他元素的z-index层叠顺序设置，而直接使用真实世界的3D视角进行渲染。
       解决方案：父级，任意父级，非body级别，设置overflow:hidden可恢复和其他浏览器一样的渲染。或设置一个足够大的translateZ值，如100px。
    2、元素应用了transform属性之后，就会变得像应用了position:relative;，提升了元素的垂直地位(层叠水平)。
    3、非IE浏览器下，transform限制position:fixed;的跟随效果，直接降级变成position:absolute;的表现。
    4、在IE9+/FireFox浏览器下，无论是overflow容器还是嵌套子元素，只要有transform属性，就会hidden溢出的absolute元素；
       Chrome/Opera浏览器下，只有嵌套元素含有transform属性的时候，absolute元素才会被overflow隐藏。
    5、以前，我们设置absolute元素宽度100%, 则都会参照第一个非static值的position祖先元素计算，没有就window。（请参考#position）
       现在，如果所有绝对定位图片100%宽度，都是相对设置了transform的容器计算了。（假设嵌套关系为：absolute/relative/window > transform > absolute）
#   box-shadow:
（该属性在 IE9+ 浏览器下支持）
单个盒子阴影时，"长度值"可以是两个、三个或者四个 ———— x偏移量 y偏移量 [模糊半径 [发散半径]]
长度值的前后也可插值 ———— inset x偏移量 y偏移量 [模糊半径 [发散半径]]  ，  x偏移量 y偏移量 [模糊半径 [发散半径]] 颜色值  ,  inset x偏移量 y偏移量 [模糊半径 [发散半径]] 颜色值
盒子拥有多个阴影时，阴影值之间通过 "," 进行分隔
当指定 "inset" 时，阴影会描绘在边框的内侧，并且位于背景的上方和内容的下方
模糊半径是不允许负值的（会默认置0）
对于颜色值，其他浏览器默认是 currentColor, 而 Safari 浏览器则默认是 transparent。
与 filter属性的drop-shadow()相比较：
    1、box-shadow支持任意阴影叠加，而drop-shadow()只能声明一个阴影
    2、box-shadow支持inset内置阴影
    3、对于浏览器的兼容性，box-shadow要比drop-shadow()要好
    4、但是，box-shadow的阴影是不符合现实世界的投影规则的，但drop-shadow()的符合
#   box-sizing:
（该属性在 IE8+ 浏览器下支持）
默认的盒模型是"content-box"，即在一般情况下，为DOM结点声明width和height时，是声明content-box的大小。那么，元素的总宽度 = 声明的width + padding的width X 2 + border的width X 2
其他值：
border-box————当声明width和height值时，该值已经包含了padding和border的大小，即声明了整个DOM结点的大小。那么，元素的总宽度 = 声明的width
#   table-layout:
auto————默认值。由内容决定对应的单元格在表格中的大小
fixed————其作用在于，让表格布局（包括 table 元素以及 display 为 table 的元素）固定，也就是表格的宽度不是跟随单元格内容多少自动计算尺寸。
    而是通过设置表格与列的宽度，或者设置表格第一行单元格的宽度来确定余下列的宽度
    （这个在某个单元格的内容需要溢出省略时十分有用）
#   animation:
#   animation-delay:
#   animation-duration:
#   animation-iteration-count:
#   animation-name:
可以设置过渡或动画的属性，请参考：https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties
#   animation-play-state:
#   animation-timing-function:
#   animation-fill-mode:
#   transition:
作用：平滑地改变CSS的值
#   transition-delay:
#   transition-duration:
#   transition-property:
可以设置过渡或动画的属性，请参考：https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties
特殊关键词：
none————不支持任何属性发生过渡
all————所有可以进行过渡的属性均进行过渡处理
< keyframeName>————自定义的 keyframe 名称
需要注意的是，一旦声明了简写的css属性作为值（例如background），那么该简写属性的子属性也可能成为了过渡属性（如果该子属性出现在可过渡列表中）
#   transition-timing-function:
#   background-clip:
CSS3新增属性（IE9+支持）
border-box————从border区域向外裁剪背景。（即不在 border-box 的背景图片部分被切除）
padding-box————从padding区域向外裁剪背景。（即不在 padding-box 的背景图片部分被切除）
content-box————从content区域向外裁剪背景。（即不在 content-box 的背景图片部分被切除）
no-clip————从border区域向外裁剪背景。
备注说明：Firefox 1.0 ~Firefox 3.6支持老的解析：border和padding，但是并不支持content以及后来的content-box值。
#   backface-visibility:
#   resize:
作用：用户可改变该块级元素的大小。
起作用的前提：overflow属性（值可以是auto、hidden或scroll）。
none————用户不可以改变元素的大小
both————用户在 x 和 y 方向均可以改变元素的大小。
horizontal————用户只可在 x 方向均可以改变元素的大小。
vertical————用户只可在 y 方向均可以改变元素的大小。
#   direction:
#   page:
#   unicode-bidi:
#   align-content:
#   align-items:
#   align-self:
#   alignment-baseline:
#   all:
#   animation-direction:
#   background-blend-mode:
#   background-origin:
CSS3新增属性（IE9+支持）
border————从border区域开始显示背景。
padding————从padding区域开始显示背景。
content————从content区域开始显示背景。
#   background-position-x:
#   background-position-y:
#   background-repeat-x:
#   background-repeat-y:
#   baseline-shift:
#   border-image-outset:
#   border-image-repeat:
#   border-image-slice:
#   border-image-source:
#   border-image-width:
#   buffered-rendering:
#   caption-side:
#   clip-path:
#   clip-rule:
#   color-interpolation:
#   color-interpolation-filters:
#   color-rendering:
#   counter-increment:
此属性通常与 counter() 计数器方法一起放置于要显示相应计数值的选择器的伪元素内(即选择器后面跟着 :before 或 :after )，
    与content属性一起使用。属性值：name1 [number name2 number ...]。 name* 表示唯一的计数源，number是递增量(默认为1)。
选择器执行该属性才会执行content属性。另外，如果该元素的display属性为none或hidden，计数值是不会增加的。
关于计数器，
counter( name [, style] )：此方法用于输出计数源的值，主要用在 content 属性内。style的参数值可以是 list-style-type 支持的那些值。
counters( name, separator )：此方法用于输出带有子序号的前缀。使用方法与 counter() 基本一致。
#   counter-reset:
此属性放置于要计数的选择器。
属性值为 name1 [number name2 number ...]
 name* 是一个标识符，用于声明唯一计数源，number是起始的数值(默认为0)，支持负值。
例如，ol标签应用counter-reset属性，li标签应用counter-increment属性，值均为sectioncounter，再配合content属性，以及counter计数器就可以实现递增的效果了。
#   cx:
#   cy:
#   dominant-baseline:
#   empty-cells:
#   fill:
#   fill-opacity:
#   fill-rule:
#   flex:
#   flex-basis:
#   flex-direction:
#   flex-flow:
#   flex-grow:
#   flex-shrink:
#   flex-wrap:
#   flood-color:
#   flood-opacity:
#   font-feature-settings:
#   font-kerning:
#   font-stretch:
#   font-variant:
#   font-variant-ligatures:
#   image-rendering:
#   isolation:
#   justify-content:
#   lighting-color:
#   marker:
#   marker-end:
#   marker-mid:
#   marker-start:
#   mask:
#   mask-type:
#   max-zoom:
#   min-zoom:
#   mix-blend-mode:
#   motion:
#   motion-offset:
#   motion-path:
#   motion-rotation:
#   object-fit:
#   object-position:
#   order:
#   orientation:
#   orphans:
#   outline-color:
#   outline-style:
#   outline-width:
#   overflow-wrap:
#   page-break-after:
#   page-break-before:
#   page-break-inside:
#   paint-order:
#   perspective:
#   perspective-origin:
#   r:
#   rx:
#   ry:
#   shape-image-threshold:
#   shape-margin:
#   shape-outside:
#   shape-rendering:
#   speak:
#   stop-color:
#   stop-opacity:
#   stroke:
#   stroke-dasharray:
#   stroke-dashoffset:
#   stroke-linecap:
#   stroke-linejoin:
#   stroke-miterlimit:
#   stroke-opacity:
#   stroke-width:
#   tab-size:
#   text-align-last:
#   text-anchor:
#   text-combine-upright:
#   text-orientation:
#   touch-action:
#   transform-origin:
该属性用于设置元素变形的原点。（即相对于左上角的偏移量，默认为 50% 50% 或 50% 50% 0 ）
由于transform可能分为2D转换和3D转换，因此值的个数有可能达到3个。
单值时，如果值的类型是非关键词，则设置的X方向上的值，其余方向则是默认值。
当值的类型出现关键词时，X和Y方向的偏移值的顺序可以更换。例如 right top 和 top right 是一样的，2px left 和 left 2px 也是一样的。
值的类型可以关键词、百分比值、带单位的length值，允许负值。
值中的关键词与大小的对应关系：
left————0%
center————50%
right————100%
top————0%
bottom————100%
#   transform-style:
#   unicode-range:
#   user-zoom:
#   vector-effect:
#   webkit-app-region:
    带有前缀的属性，如果有相应的无前缀属性，那么无前缀属性应当放到带有前缀的属性的后面，因为通常两者的作用是不一样的。
#   webkit-appearance:
#   webkit-background-clip:
#   webkit-background-composite:
#   webkit-background-origin:
#   webkit-border-after:
#   webkit-border-after-color:
#   webkit-border-after-style:
#   webkit-border-after-width:
#   webkit-border-before:
#   webkit-border-before-color:
#   webkit-border-before-style:
#   webkit-border-before-width:
#   webkit-border-end:
#   webkit-border-end-color:
#   webkit-border-end-style:
#   webkit-border-end-width:
#   webkit-border-horizontal-spacing:
#   webkit-border-image:
#   webkit-border-start:
#   webkit-border-start-color:
#   webkit-border-start-style:
#   webkit-border-start-width:
#   webkit-border-vertical-spacing:
#   webkit-box-align:
#   webkit-box-decoration-break:
#   webkit-box-direction:
#   webkit-box-flex:
#   webkit-box-flex-group:
#   webkit-box-lines:
#   webkit-box-ordinal-group:
#   webkit-box-orient:
#   webkit-box-pack:
#   webkit-box-reflect:
#   webkit-clip-path:
#   webkit-column-break-after:
#   webkit-column-break-before:
#   webkit-column-break-inside:
#   webkit-column-count:
#   webkit-column-gap:
#   webkit-column-rule:
#   webkit-column-rule-color:
#   webkit-column-rule-style:
#   webkit-column-rule-width:
#   webkit-column-span:
#   webkit-column-width:
#   webkit-columns:
#   webkit-filter:
#   webkit-font-size-delta:
#   webkit-font-smoothing:
#   webkit-highlight:
#   webkit-hyphenate-character:
#   webkit-line-break:
#   webkit-line-clamp:
#   webkit-locale:
#   webkit-logical-height:
#   webkit-logical-width:
#   webkit-margin-after:
#   webkit-margin-after-collapse:
#   webkit-margin-before:
#   webkit-margin-before-collapse:
#   webkit-margin-bottom-collapse:
#   webkit-margin-collapse:
#   webkit-margin-end:
#   webkit-margin-start:
#   webkit-margin-top-collapse:
#   webkit-mask:
#   webkit-mask-box-image:
#   webkit-mask-box-image-outset:
#   webkit-mask-box-image-repeat:
#   webkit-mask-box-image-slice:
#   webkit-mask-box-image-source:
#   webkit-mask-box-image-width:
#   webkit-mask-clip:
#   webkit-mask-composite:
#   webkit-mask-image:
#   webkit-mask-origin:
#   webkit-mask-position:
#   webkit-mask-position-x:
#   webkit-mask-position-y:
#   webkit-mask-repeat:
#   webkit-mask-repeat-x:
#   webkit-mask-repeat-y:
#   webkit-mask-size:
#   webkit-max-logical-height:
#   webkit-max-logical-width:
#   webkit-min-logical-height:
#   webkit-min-logical-width:
#   webkit-padding-after:
#   webkit-padding-before:
#   webkit-padding-end:
#   webkit-padding-start:
#   webkit-perspective-origin-x:
#   webkit-perspective-origin-y:
#   webkit-print-color-adjust:
#   webkit-rtl-ordering:
#   webkit-ruby-position:
#   webkit-tap-highlight-color:
#   webkit-text-combine:
#   webkit-text-decorations-in-effect:
#   webkit-text-emphasis:
#   webkit-text-emphasis-color:
#   webkit-text-emphasis-position:
#   webkit-text-emphasis-style:
#   webkit-text-fill-color:
#   webkit-text-orientation:
#   webkit-text-security:
#   webkit-text-stroke:
#   webkit-text-stroke-color:
#   webkit-text-stroke-width:
#   webkit-transform-origin-x:
#   webkit-transform-origin-y:
#   webkit-transform-origin-z:
#   webkit-user-drag:
#   webkit-user-modify:
#   webkit-user-select:
#   webkit-writing-mode:
#   widows:
#   will-change:
#   writing-mode:
#   x:
#   y:
#   css-text:
#   length:
#   parent-rule:
#   css-float:
#   item:  
#   get-property-value:
#   get-property-priority:
#   set-property:
#   remove-property: