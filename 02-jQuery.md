# jQuery

>是一个快速，小巧，且功能丰富的javascript库。它使HTML文档的遍历和操作、事件处理、动画和Ajax等操作变得更加简单，并提供了一个易于使用的API，可以跨多种浏览器工作。JQuery集多功能性和可扩展性于一身，改变了数百万人编写javascript的方式
>
>*jQuery是一个JavaScript函数库*
>		*jQuery是一个轻量级的“写得少，做得多”的JavaScript库*

## 1.jquery的优势

>- 不污染顶级变量，   它的变量都是保存在一个叫做jQuery的类里面
>- 出色的浏览器兼容性
>- 链式操作
>- 隐士迭代
>- 行为层和结构层的分离
>- 丰富的插件支持

## 2.jQuery的引入

>jQuery符号，
>
>- jQuery把所有功能全部封装在一个全局变量jQUery中，而$也是一个合法的变量名，它是变量jQuery的别名
>- *jQuery.noConflict()*     释放$符号

## 3.jQuery书写

>相当于load     有三种写法
>
>```javascript
>$(document).ready(function () {
>        $('div').addClass('div');
>    })
>$().ready(function () {
>
>    })
>$(function () {
>
>    })
>```
>
>

## 3.jQuery的方法

>**jquery会隐士迭代数组**
>
>- **css()**   直接书写*('color','red')*      对象的形式*({'color':'red'})*
>- **$(this).index()**     返回当前元素的索引
>- **$(this)**     返回当前元素
>- **text (文本)**      改变当前元素的文本     相当于innerText
>- **html (要添加的内容)**      改变元素内的标签    相当于innerHTML
>- **val()**      获取input的value
>- **add()**        $('a').add('p')     把p放到a的集合中

## 4.jQuery选择器 

>返回的对象的是jQuery对象，类似数组，每个元素都是引用了DOM节点的对象
>
>不会返回 undefined 或者 null      如果不存在会直接返回空数组
>
>- 基本选择器
>
>  - **#id**  根据给定的id匹配一个元素
>  - **.class**    根据给定的className匹配一个元素
>  - **element**    根据给定的标签名称匹配一个元素
>  - *****      通配符选择器    *慎用*
>
>- 多项选择器
>
>  - **$('a,div,p')**    将每一个选择器匹配到的元素合并后一起返回，可以指定任意多个选择器，并将匹配到的元素合并到一个结果内，如果有多个选择器匹配到的元素一样的话，只会返回一个
>  - 返回的数组顺序会按照html结构的顺序返回
>
>- 层级选择器
>
>  - **$('祖先 后代')**     匹配给定祖先元素后面的所有后代元素
>  - **$('父 > 子')**      匹配给定父元素的子元素
>  - **$('prev + next')**    匹配紧接在prev元素后的第一个next元素
>  - **$('prev~siblings')**     匹配prev元素之后的所有sublings元素，他们必须是在同一层级中
>
>- 属性选择器
>
>  - **[class]**      匹配带有class属性的元素
>  - **[class = 'aa']**      等于aa
>  - **[class ^= 'aa']**      aa开头
>  - **[calss $= 'aa']**      aa 结尾
>  - **[class *= 'aa']**      包含aa
>  - **[class != 'aa']**     只要class不等于aa的所有元素，包括没有class的元素
>  - **[class] [type] [alt]**    匹配满足多个条件的元素
>
>- 过滤器
>
>  - **div p:first-child**     匹配div下面的第一个元素，并且必须是p
>
>  - **div p:last-child**    匹配div下面的最后一个元素，并且必须是p
>
>  - **:nth-child (n | even | odd | formula )** 第n个元素，*下标从1开始*
>
>  - **:nth-last-child ( n | even | formula )** 倒数第n个元素，*下标从1开始*
>
>  - **:only-child** 父元素只有它一个子元素，它没有任何兄弟元素，返回这个元素
>
>  - >要求父元素中只要包含该标签，就有返回值 ↓
>
>  - **:first-of-type**     
>    **:last-of-type**
>    **:nth-of-type(n|even|odd|formula)**
>    **:nth-of-last-type(n|even|odd|formula)**
>    **p:only-of-type**     只要父元素里的p标签只有一个时就能找到
>
>  - *参数*
>
>    - n    匹配子元素序号，必须为整数，从1开始
>    - even    匹配所有偶数元素
>    - odd    匹配所有奇数元素
>    - formula     使用特殊公式
>
>-  表单相关
>
>  - **:input**      可以选择input    textarea   select   button 标签
>  - **:text**    匹配所有的单行文本框，和 *input[type='text']* 一样
>  - 其他的input的type也可以   *:password*  *:radio*   等等
>  - **:enabled**    匹配所有可用表单元素
>  - **:disabled**    匹配所有不可用的表单元素
>  - **:checked**  匹配所有选中的元素(复选框、单选等，select中的option)
>  - **:selected**     匹配选中的option元素
>
>- 查找和过滤的方法
>
>  - **$('p').find('a')**     匹配p的后代中的所有a元素      
>  - **$('p').children('a')**     匹配p的子元素中的所有a元素，如果没有参数，默认为p下面的所有子元素，(不包含孙子，后代)
>  - **$('p').parent()**   匹配p元素的父亲
>  - **next()**    匹配下一个紧接着的兄弟元素
>  - **prev()**    匹配上一个紧接着的兄弟元素
>  - **eq()**     匹配返回的数组的第几个元素    -n为倒数第几个
>  - **siblings()**     匹配所有的兄弟元素    可以带参数
>  - **filter(expr | object| element | fn)**     筛选出与指定表达式匹配的元素集合
>  - 参数
>  - expr：字符串值，包含供匹配当前元素集合的选择器表达式
>  - object：现有的jQuery对象，以匹配当前的元素
>  - element：一个用于匹配元素的DOM元素
>  - fn：一个函数用来作为测试元素的集合

## 5.jQuery事件

>- **click()**    点击事件
>- **dblcilck()**     双击事件
>- **mousedown()**     鼠标按下
>- **mouseup()**   鼠标弹起
>- **mouseenter()**    鼠标进入时触发
>- **mouseleave()**    鼠标移出时触发
>- **hover()**       参数为两个函数，第一个函数为移入，第二个移出
>- **mouseover()**     鼠标进入指定元素及其子元素时触发   *冒泡*
>- **mouserout()**     鼠标移出指定元素及其子元素时触发    *冒泡*
>- **mousemove()**      鼠标在元素内部移动时触发
>- **scroll()**      滚动指定元素时触发，前提是元素有滚动条
>- **focus()**     获取焦点触发
>- **blur()**    失去焦点触发
>- **change()**    当元素的值发生改变是触发  输入的时候不会检测，而是外界刺激的时候，才会检测
>- **select()**      当textarea或可输入文本类型的input中的文本被选择时触发
>- **submit()**      提交表单时触发    给form添加
> -  return false时 表单不会被提交
> - button 在form中时 在除了IE的其他内核浏览器中 作为submit存在
>
>*键盘事件*
>
>- **keydown()**      当按键按下时触发
>- **keyup()**     按键弹起时触发
>- **keyperss()**      按下字符按键时触发， 就是说用户按了一个能在屏幕上输出字符的按键keypress事件才会触发）。一直按着某按键则会不断触发。
>
>*其他标签*
>
>- **ready()**     当DOM加载完成时触发
>- **resize()**      当调整浏览器窗口大小时触发    只能绑定咋window上
>
>*事件绑定或取消*
>
>- **on(events,[selector],[data],fn)**      在选择元素上绑定一个或多个事件的事件处理函数    *events事件类型*      *[selector]:选择器*
>- *on可以绑定动态生成的元素。*       
>-  **off(events,[selector],[fn])**      解绑事件
>- **one(type,[selector],[data],fn)**     绑定一个一次性事件处理函数
>
>*注意*
>
>​	return fasle    阻止冒泡

## 6.jquery动画

>- **animate()**     可以实现任意动画效果，需要传递的参数时DOM元素的最终的css状态和时间      px可以不写
>- **stop()**     终止动画  会将当前的动画终止掉，直接开始后面的动画；不会产生排队现象，没有进行事件操作动画因排队现象而继续运行；
>- **delay(1000)**         延迟1s    两个动画间隔1s
>- **show()**     显示元素     控制宽高和透明度  
>- **hide()**      隐藏元素       控制宽高和透明度
>- **toggle() **     显示隐藏的结合
>- **fadeIn()**     淡入    通过opacity属性实现
>- **fadeOut()**     淡出      通过opacity属性实现
>- **fadeToggle()**      淡入淡出结合
>- **slideUp()**       垂直方向逐渐收缩
>- **slideDown()**
>- **slideToggle()**
>- *注意：建议动画之前+.stop()结束其他动画*      
>- *单位：时间毫秒/fast/slow*

## 7.jquery插件开发方法

>- **$.extend()**     来扩展jquery
>- **$.fn**    向jquery添加新的方法
>- **$.widget()**      应用jquery Ui的部件工厂方式创建