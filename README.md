# 1. CSS的介绍

## 1.1 CSS、HTML、JavaScript各司其职

Cascading Style Sheets

html: 结构

CSS: 表现

JavaScript: 交互、动作

CSS - 美化网页， 包括字体、颜色、边距、高度、宽度、背景图片、网页定位、网页浮动



## 1.2 发展史

CSS1.0

CSS2.0 DIV（块） +CSS， HTML与CSS结构分离的思想，网页变得简单，SEO

CSS2.1 浮动、定位

CSS3.0 圆角， 阴影，动画······浏览器兼容性





## 1.3 尝试

文件存放格式：

要标准

## ![截屏2021-04-05 10.10.40](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-05 10.10.40.png)



index.html:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

<!--    规范
<style>可以在这里写CSS代码，但是一般不这么写，只是为了练习方便</style>
    CSS的基础语法：
    选择器{
        声明1;
        声明2;
    }
    每一个声明，最好使用";"结尾

-->

<!--

        h1{
            color: lightgoldenrodyellow;
        }
    </style>
    -->


<!--    把内容/html和表现/CSS分离， 但是连接起来-->
    <link rel="stylesheet" href="style.css">

</head>
<body>
<h1>测试</h1>
</body>
</html>
```



style.css:

```css
h1{
    color: aquamarine;
}
```

测试结果：

![截屏2021-04-05 10.19.24](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-05 10.19.24.png)



### CSS的优势

- 内容和表现分离
- 网页结构表现统一， 可以实现复用
- 样式十分丰富
- 建议使用独立于html的css文件
- 利用SEO，容易被搜索引擎收录



## 1.4 CSS的3种导入方式

- 行内样式
- 内部样式
- 外部样式

优先级(就近原则)：行内样式>内部样式>外部样式

谁离元素最近就跟随哪个。



index.html

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
<!--比较优先级-->

  
<!--    2. 内部样式-->
    <style>
        h1{
            color: bisque;
        }
    </style>
</head>
<body>

<h1>标题</h1>
    <!--1. 行内样式： 在标签元素中，编写一个style属性，随后编写样式即可 -->
    <!--
<h1 style="color: aquamarine">标题</h1>
-->

</body>
</html>
```



Style.css

```css
h1{
    color: black;
}
/*此处是注释
快捷键：
command + /

  */
```



拓展：

外部样式两种写法

- 链接式

  ```html
  <link rel="stylesheet" href="style.css">
  ```

  

- 导入式

  @import式CSS2.1特有的

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        @import "style.css";
    </style>
  
</head>
<body>

<h1>hahah</h1>
</body>
</html>
```

@import必须放在style标签中



# 2.选择器

> 选择器的作用： 选择页面上的某一个元素的某一类元素，然后美化



## 2.1 基本选择器

1. 标签选择器 - 选择一类标签 标签{}
2. 类选择器 class - 选择所有class属性一致的标签， 跨标签   .类名{}
3. id 选择器 全局唯一  #id{}

优先级；不遵循就近原则：固定的

id选择器>class选择器>标签选择器



1标签选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*标签选择器， 就选择到页面上所有的这个标签的元素*/
        /*选中h1*/
        h1{
            color: darkblue;
            background: bisque;
            border-radius: 24px;
        }
        /*选中p*/
        p{
            font-size: 35px;
            color: aquamarine;
        }
    </style>
</head>
<body>
<h1>ahahhah</h1>
<p>lalalall paragraph</p>
<p>fgfnh</p>
</body>
</html>
```



2类选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*类选择器的格式 .class的名称{} */
        .alan{
            color: darkblue;
        }
        .itari{
            color: khaki;
        }
        .natsume{
            color: yellow;
        }
        .hinata{
            color: aquamarine;
        }
    </style>
</head>
<body>
<h1 class="natsume">title1</h1>
<h1 class="itari">title2</h1>
<h1 class="alan">title3</h1>

<p class="hinata">title4</p>
</body>
</html>
```





3id选择器

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        /*id选择器
        id必须保证全局唯一； 唯一性
        #id 名称 {}
        */

        #natsume{
            color: aliceblue;
        }
    </style>
</head>
<body>
<h1 id="natsume">title1</h1>
<h1 id="itari">title2</h1>
<h1 id = "alan">title3</h1>
<h1>title4</h1>
</body>
</html>
```



## 2.2 层次选择器

1. 后代选择器
2. 子选择器
3. 相邻兄弟选择器
4. 通用选择器





1. 后代选择器 祖爷爷 爷爷 爸爸 你

```html
/*后代选择器
*/
/*body元素的后面都变了*/
body p{
    color: yellow;
}
```



2. 子选择器 一代，儿子

```html
 /*子选择器
 只有body后第一代有
*/
 /*body元素的后面都变了*/
 body>p{
     background-color: darkblue;
 }
```



3. 相邻兄弟选择器 同辈 只有一个 相邻+向下

```html
        /*兄弟选择器*/
        .active+p{
            background-color: antiquewhite;
        }

<p>p0</p>
<p class="active">p1</p>
<p>p2</p>
<p>p3</p>
```

![截屏2021-04-05 13.24.16](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-05 13.24.16.png)



4. 通用选择器

```html
.active~p{
    background-color: darkslateblue;
}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p{
            background-color: khaki;
        }

        /*后代选择器
        */
        /*body元素的后面都变了*/
        body p{
            color: yellow;
        }
        /*子选择器
        只有body后第一代有
       */
        /*body元素的后面都变了*/
        body>p{
            background-color: darkblue;
        }

        /*通用选择器 当前选中元素的向下的所有兄弟元素*/
        .active+p{
            background-color: antiquewhite;
        }
        .active~p{
            background-color: darkslateblue;
        }


    </style>
</head>
<body>
<p>p0</p>
<p class="active">p1</p>
<p>p2</p>
<p>p3</p>
<ul>
    <li>
        <p>p4</p>
    </li>
    <li>
        <p>p5</p>
    </li>
    <li>
        <p>p6</p>
    </li>
</ul>

</body>
</html>
```

![截屏2021-04-05 13.28.24](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-05 13.28.24.png)



## 2.3结构“伪类选择器”

伪类： 带“：”



```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Title</title>

<!--  避免使用class，id选择器-->
  <style>

<!--    ul的第一个子元素-->
    ul li:first-child{
      background-color: antiquewhite;
    }
  /* ul的最后一个子元素 */
    ul li:last-child{
      background-color: darkseagreen;
    }

  /*选中p1， 定位到父元素，选择当前第一个元素
  选择当前p元素的父级元素， 选中父级元素的第一个，并且是当前元素才生效
  */
    p:nth-child(1){
      background: chocolate;
    }
    p:nth-child(3){
      background: aquamarine;
    }

    /*选中父元素， 下的p元素的第二个，看的是类型*/
    p:nth-of-type(1){
      background-color: aliceblue;
    }

  </style>
</head>
<body>
<p>p0</p>
<p>p1</p>
<p>p2</p>
<p>p3</p>
<ul>
  <li>
    <p>p4</p>
  </li>
  <li>
    <p>p5</p>
  </li>
  <li>
    <p>p6</p>
  </li>
</ul>
</body>
</html>
```



![截屏2021-04-06 11.54.28](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-06 11.54.28.png)





## 2.4 属性选择器(高级、常用)

​		= 绝对等于
​        *= 包含这个元素
​        ^= 以这个开头
​        $= 以这个结尾



| =“”  |   绝对等于   |
| :--: | :----------: |
| *=“” | 包含这个元素 |
|  ^=  |  以这个开头  |
|  $=  |  以这个结尾  |



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        .demo a{
            float: left;
            display: block;
            height: 50px;
            width: 50px;
            border-radius: 10px;
            background: cornflowerblue;
            text-align: center;
            color: gray;
            text-decoration: none; /*去掉下划线*/
            margin-right: 5px;
            font: bold 20px/50px Arial;
        }


    /*    存在id属性的元素/第一个，
    属性选择器：a[带有什么属性]{}
    */

        /*属性名 属性名=属性值（正则）
        = 绝对等于
        *= 包含这个元素
        ^= 以这个开头
        $= 以这个结尾
        */
        a[id]{ /*1, 1nd*/
        background: yellow;
        }
        a[id=first]{/*1*/
            background: chocolate;
        }
        a[id=second]{ /*1nd*/
            background: yellow;
        }
        a[class="links item"]{ /*3/4/5*/
            background: gold;
        }


        a[class*="links"]{ /*1 1nd 2 3 4 5 */
            background: dimgrey;
        }

    /*    选中href中以http开头的元素 1*/
        a[href^=http]{
            background: cornflowerblue;
        }


        /*$= 以···结尾， 7 8 */
        a[href$=pdf]{
            background: darkorange;
        }

    </style>
</head>
<body>
<p class="demo">
    <a href="http://baidu.com" class="links item first" id="first">1</a>
    <a href="" class="links item first" id="second">1nd</a>

    <a href="" class="links item active" target="_blank" title="test">2</a>
    <a href="images/1243546.html" class="links item"  >3</a>
    <a href="images/1232.png" class="links item">4</a>
    <a href="images/12322132.jpg" class="links item">5</a>
    <a href="abc">6</a>
    <a href="/a.pdf">7</a>
    <a href="/sbc.pdf">8</a>
    <a href="sbc.doc">9</a>
    <a href="abcd/doc" class="link item last">10</a>
</p>
</body>
</html>
```





![截屏2021-04-06 12.19.20](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-06 12.19.20.png)







![截屏2021-04-06 12.20.50](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-06 12.20.50.png)





# 3. 美化网页元素

## 3.1为什么要美化网页

1. 有效的传递页面信息
2. 美化网页，吸引客户
3. 凸显页面主题
4. 提高用户的体验





标签*span： 重点要突出的字，使用span标签套起来

 ```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>

    <style>
        #title1{
            font-size: 40px;
            font-family: Times New Roman;


        }
    </style>
</head>
<body>
Welcom to the <span id="title1"> happy place</span>!
</body>
</html>
 ```



## 3.2字体样式





```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>

       /*字体样式：
                font-family: 改字体
                font-size: 字体大小
                font-weight: 字体粗细
                color: 字体颜色
                */
        body{
            font-family: Times;
            color: darkgrey;
        }

        h1{
            font-size: 50px;
        }
        .p1{
            font-weight: bold;
        }


    </style>
</head>
<body>
<h1>
    小红帽
    <br>
    Little Red Riding Hood
</h1>

<p class="p1">
    “小红帽”的故事版本多达一百多个，小红帽最早的结局是被邪恶的野狼吞噬。后来，在格林兄弟笔下，勇敢的猎人杀死大野狼，救出了小红帽。在晚近的版本中，又成了小红帽用剪刀剪破大野狼的肚皮，自己拯救了自己。在某些版本中，小红帽甚至成为充满情欲的性感女郎。
</p>

<p>
    故事讲述了从前有个人见人爱的小姑娘，喜欢戴着外婆送给她的一顶红色天鹅绒的帽子，于是大家就叫她小红帽。有一天，母亲叫她给住在森林的外婆送食物，并嘱咐她不要离开大路，走得太远。小红帽在森林中遇见了狼，她从未见过狼，也不知道狼性凶残，于是告诉了狼她要去森林里看望自己的外婆。狼知道后诱骗小红帽去采野花，自己到林中小屋把小红帽的外婆吃了。后来他伪装成外婆，等小红帽来找外婆时，狼一口把她吃掉了。幸好后来一个勇敢的猎人把小红帽和外婆从狼肚里救了出来。

</p>

<p>
    Once upon a time, there was a little girl who lived in a village near the forest.  Whenever she went out, the little girl wore a red riding cloak, so everyone in the village called her Little Red Riding Hood.

One morning, Little Red Riding Hood asked her mother if she could go to visit her grandmother as it had been awhile since they'd seen each other.

"That's a good idea," her mother said.  So they packed a nice basket for Little Red Riding Hood to take to her grandmother.

When the basket was ready, the little girl put on her red cloak and kissed her mother goodbye.

"Remember, go straight to Grandma's house," her mother cautioned.  "Don't dawdle along the way and please don't talk to strangers!  The woods are dangerous."

"Don't worry, mommy," said Little Red Riding Hood, "I'll be careful."
</p>
<p>

Little Red Riding Hood StoryBut when Little Red Riding Hood noticed some lovely flowers in the woods, she forgot her promise to her mother.  She picked a few, watched the butterflies flit about for awhile, listened to the frogs croaking and then picked a few more.

Little Red Riding Hood was enjoying the warm summer day so much, that she didn't notice a dark shadow approaching out of the forest behind her...

Suddenly, the wolf appeared beside her.
</p>
<p>
"What are you doing out here, little girl?" the wolf asked in a voice as friendly as he could muster.

"I'm on my way to see my Grandma who lives through the forest, near the brook,"  Little Red Riding Hood replied.

Then she realized how late she was and quickly excused herself, rushing down the path to her Grandma's house.

The wolf, in the meantime, took a shortcut...
</p>
<p>

The wolf, a little out of breath from running, arrived at Grandma's and knocked lightly at the door.

"Oh thank goodness dear!  Come in, come in!  I was worried sick that something had happened to you in the forest," said Grandma thinking that the knock was her granddaughter.

The wolf let himself in.  Poor Granny did not have time to say another word, before the wolf gobbled her up!

The wolf let out a satisfied burp, and then poked through Granny's wardrobe to find a nightgown that he liked.  He added a frilly sleeping cap, and for good measure, dabbed some of Granny's perfume behind his pointy ears.

A few minutes later, Red Riding Hood knocked on the door.  The wolf jumped into bed and pulled the covers over his nose.  "Who is it?" he called in a cackly voice.

"It's me, Little Red Riding Hood."
</p>
<p>
"Oh how lovely!  Do come in, my dear," croaked the wolf.
</p>
<p>
When Little Red Riding Hood entered the little cottage, she could scarcely recognize her Grandmother.

"Grandmother!  Your voice sounds so odd.  Is something the matter?" she asked.

"Oh, I just have touch of a cold," squeaked the wolf adding a cough at the end to prove the point.

"But Grandmother!  What big ears you have," said Little Red Riding Hood as she edged closer to the bed.

"The better to hear you with, my dear," replied the wolf.
</p>
<p>
"But Grandmother!  What big eyes you have," said Little Red Riding Hood.
</p>
<p>
"The better to see you with, my dear," replied the wolf.
</p>
<p>
"But Grandmother!  What big teeth you have," said Little Red Riding Hood her voice quivering slightly.
</p>
<p>
"The better to eat you with, my dear," roared the wolf and he leapt out of the bed and began to chase the little girl.
</p>
<p>
Almost too late, Little Red Riding Hood realized that the person in the bed was not her Grandmother, but a hungry wolf.
</p>
<p>
She ran across the room and through the door, shouting, "Help!  Wolf!" as loudly as she could.
</p>
<p>

A woodsman who was chopping logs nearby heard her cry and ran towards the cottage as fast as he could.
</p>
<p>
He grabbed the wolf and made him spit out the poor Grandmother who was a bit frazzled by the whole experience, but still in one piece."Oh Grandma, I was so scared!"  sobbed Little Red Riding Hood, "I'll never speak to strangers or dawdle in the forest again."
</p>
<p>
"There, there, child.  You've learned an important lesson.  Thank goodness you shouted loud enough for this kind woodsman to hear you!"
</p>
<p>
The woodsman knocked out the wolf and carried him deep into the forest where he wouldn't bother people any longer.
</p>
<p>
Little Red Riding Hood and her Grandmother had a nice lunch and a long chat.
</p>

</body>
</html>
```



![截屏2021-04-06 14.54.27](/Users/wangminghan/Library/Application Support/typora-user-images/截屏2021-04-06 14.54.27.png)









```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        p{
            font: oblique 30px "Times New Roman";
        }
    </style>
</head>
<body>
<p>
    Once upon a time, there was a little girl who lived in a village near the forest.  Whenever she went out, the little girl wore a red riding cloak, so everyone in the village called her Little Red Riding Hood.
</p>
</body>
</html>
```





## 3.3 文本样式

1. 颜色
2. 文本对齐方式
3. 首行缩进
4. 行高
5. 装饰



```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        h1{

            /*颜色：
            RGB： 0~F
            RGBA: + A: 0~1

            */
            /*
            color: #6b6be9;
            */
            /*
            or,
            color: rgb(0,255,255);
            */

            color: rgba(0,255,255,0.5);

            /*text-align文本排版
            center, left, right
            行高和块的高度一致时，就可以上下居中*/

            text-align: center;
        }
        .p1{
            text-indent: 2em; /*tab*/
        }
        .p3{
            background: aquamarine;
            height: 300px; /*背景高度*/
            line-height: 300px;/*行高*/
            /*行高和块的高度一致时，就可以上下居中*/
        }

        /*下划线，中划线/删除线，上划线*/
        .a{
        text-decoration: underline;
        }
        .b{
            text-decoration: line-through;
        }
        .c{
            text-decoration: overline;
        }

    </style>
</head>
<body>

<p class="a">1256</p>
<p class="b">1256</p>
<p class="c">1256</p>


<h1>Introduction</h1>
<p class="p1">
    Once upon a time, there was a little girl who lived in a village near the forest.
</p>
<p class="p3">
    Whenever she went out, the little girl wore a red riding cloak, so everyone in the village called her Little Red Riding Hood.
</p>
</body>
</html>
```

