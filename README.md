# css
# 多类名选择器
- 在style里写的样式，可以在body的div等中调用,且可调用多个，样式类名中间用空格隔开。
- 例：<div class="pink font20">111</div>
- 样式显示效果跟html元素类名先后没有关系，受CSS样式书写上下顺序有关。可以调用多次样式类名

# 类名选择器（class选择器）
- <div class="nav"> 这个div的名字就是nav,nav就是div  这个div就是nav
- 我们想要把div找到 div{} .nav{}

# id选择器 好比身份证号，唯一的，只能使用一次
- 例<div id="last"> #定义 id调用

# 通配符选择器(开发基本不用）
- 用*表示所有的意思
例<style>
*{
}
</style>

CSS字体样式属性
font-size字体字号大小（要带单位） 常用单位px像素 em
font-family:"字体"  字体可输入英文名称，输入Unicode编码兼容性更好
font-weight:字体粗细（可以直接输入数字,建议用数字）  bold粗体700   normal 普通400
font-style: 字体风格 normal italic斜体

字体连写
选择器{font: font-style font-size/line-height font-family}
必须保留font-size和font-family属性(否则报错），其余可以省略

text-indent:段落首行缩进 1em为一个字符 em是字符单位
text-align:center  文字居中
text-decoration:文本装饰
none取消装饰 underline下划线 
 文本格式化标签样式 em和i 倾斜    strong和b 粗细  u和ins 下划线 s和del 删除线


复合选择器
1后代选择器
用来选择元素或元素组的后代，写法是把外层标签写在前面，内层标签写在后面，中间用空格隔开。标签有嵌套，内层标签就为外层标签的后代
例：ul li a {}
2子代选择器：指的是亲儿子（大于号分割）
 例 ul li > a {}
3交集选择器 标签连写 既又的关系  既是div又叫red 使用的较少
例:div.red
4并集选择器：用逗号隔开，逗号代表和的意思，集体声明，适合于相同样式
例:div,p,span{}

链接伪类选择器
:link 链接未访问过的状态
:visited 链接访问过的状态
:hover 鼠标经过的状态
:active 鼠标按下的状态
书写顺序不要颠倒
例:a:link

ctrl+/快速添加注释

sublime快捷键
生成标签，直接输入标签名按tab键即可
生成多个相同标签加上*个数即可
有父子级关系的标签，用> 比如ul>li
兄弟关系的标签，用+ 比如div+p
生成带有类名或id名字的,写.demo或#id名按下tab键即可

标签（元素）显示模式（display)
块级元素block-level
每个块元素通常占据一整行或多行，可设置高度宽度对齐等属性，常见块元素有<h1>~<6>,p,div ul ol li，div是典型
块元素特点：宽度默认是页面全部占满，可以容纳内联元素和其他块元素
行内元素inline-level
典型的行内元素是<span>
特点：每个行内元素都可以在一行上，高宽无效，水平方向的padding和margin可以设置，垂直方向无效。默认宽度是标签内内容的宽度，行内元素只能容纳文本或其他行内元素（a特殊因为a可以放块级元素)
行内块元素inline-block
img/ input/  td
把块级元素转换为行内元素
例div{
display:inline;
}
把行内元素转换为块级元素
例：span{
display:block;
}
把行内、块元素转换为行内块元素
例a{
display：inline-block;
} 

行高的问题line-height
行高等于height 文字会垂直居中
若行高大于height，文字会向下

三大特性
层叠性：书写时如果出现冲突，后边的样式覆盖前面的样式。样式不冲突不会层叠（就近原则，长江后浪推前浪）
继承性：子标签会继承父标签的某些样式如：文本颜色字号（子承父业）
权重（优先级） 低到高
*{}0000  div{}0001   .class0010  #id0100  写在标签内（行内）1000  !important 无穷大
权重相同则就近原则，权重可以叠加
继承的权重为0

背景
background-color:
background-image: url()
background-repeat:repeat 背景平铺
background-repeat:no-repeat
background-repeat:repeat-x x轴向平铺 
background-repeat:repeat-y y轴向平铺
background-position:水平方向 垂直方向 两个参数 top left  bottom下 right右
1.position后面可以跟方位名词，之间没有上下顺序。
2.position后面如果只写一个方位名词，另一个默认是居中
3.positon后面也可以跟值px,x轴值在前，y轴值在后 (left和top)
background-attachment: fixed（背景固定）
background-attachment: scroll（背景滚动)
背景连写 background:背景颜色 背静图片地址 背景平铺 背景滚动 背景位置  

背景透明（CSS3）
background: rgba( , , , )red green blue alpha(透明度）0~1

盒子模型（重点）
盒子边框（border)
border-width:
border-style: none（没有边框） solid（实线边框）dashed（虚线）dotted（点线）
border-color:
边框连写
border: 四边宽度 四边样式 四边颜色;
例border: 1px solid red;

边框拆开
border-top: 1px solid red; border-bottom: 1px solid red; border-left: 1px solid red; border-right: 1px solid red;

表格细线边框
border-collapse: collapse(合并相邻表格，让线变细）

内边距(padding)
padding: 10px; (上下左右10像素的
padding-left
padding-right
padding-top
padding-bottom

内边距问题
padding: 10px 20px;(上下10，左右20)
padding: 10px 20px 30px;(上10，左右20 下30)
padding: 10px 20px 30px 40px;(上10，右20 下30 左40)顺时针

外边距(margin)
margin: 10px 20px;(上下10，左右20)
margin: 10px 20px 30px;(上10，左右20 下30)
margin: 10px 20px 30px 40px;(上10，右20 下30 左40)顺时针

盒子水平居中
margin: 0 auto;(上下是0，左右是自动，水平居中对齐）
margin-left:auto; margin-right:auto (自动充满）
要实现水平居中需要满足两个条件1必须是块级元素2盒子必须指定了宽度

外边距合并
例 .xiongda{
margin-bottom: 100px;
}
.xionger{
margin-top:150px;
}
两个盒子的距离是最大的为准(150px)
嵌套块元素垂直外边距的合并
若父元素没有上内边距和边框，父元素的上外边距会与子元素的上外边距发生合并，合并后的外边距为两者中的最大值。即使父元素上边距为0，合并也会发生。
解决方案1为父元素定义一像素的上边框或上内边距border padding 
2.为父元素添加overflow::hidden

padding撑开盒子的情况
因为父盒子有宽度，给定值了，则padding会撑开
儿子没有给定宽度，用的是默认的，所以padding没有撑开盒子

圆角边框（CSS3）
border-radius: 50%; 让一个正方形变成圆圈 
border-radius: 1px 1px 1px 1px(顺时针左上开始）
两个值（左上右下开始，对角线，右上左下）

盒子阴影
语法格式 box-shadow:水平阴影 垂直阴影 模糊距离 阴影大小 阴影颜色

浮动float
为什么用浮动：让多个div在一行内显示
float: left 左对齐 float: right 右对齐

浮动特性
3个块元素盒子要在同一行，就需要全部浮动
浮动有隐藏模式转换
元素添加浮动后，转换为行内块模式
