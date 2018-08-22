~~~
style 只能获取dom 元素里的 样式 不能获取class 和外链样式中的
~~~
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        #div{
            width: 200px;
            height: 200px;
            background: red;
        }
    </style>
</head>
<body>
    <input type="button" value="样式" id="btn">
    <div id="div"></div>
    <script>
        function css(obj, attr, value) {
            if (arguments.length === 2) {
                return obj.currentStyle[attr];
            } else if(arguments.length === 3){
               obj.style[attr] = value;
            }
        }
        window.onload = function (){
            var oBtn = document.getElementById("btn");
            var oDiv = document.getElementById("div");

            oBtn.onclick = function () {
                css(oDiv, 'background', 'green');
                console.log(oDiv.currentStyle.width);
                // console.log(getComputedStyle(oDiv, false).width);
            }
        }
    </script>
</body>
</html>
```
```
然而当我用chrome浏览器测试的时候，浏览器却抛出了一个错误

Uncaught TypeError: Cannot read property ‘width’ of undefined

于是马上联想到这必定又是浏览器大战中留下来的兼容问题，于是小白开始上网搜索，总结如下：

currentStyle：获取计算后的样式，也叫当前样式、最终样式。
优点：可以获取元素的最终样式，包括浏览器的默认值，而不像style只能获取行间样式，所以更常用到。
注意：不能获取复合样式如background属性值，只能获取单一样式如background-color等。
非常遗憾的是，这个好使的东西也不能被各大浏览器完美地支持。准确地说，在我测试的浏览器中，IE8和Opera 11弹出了“object CSSStyleDeclaration”；FF 12、chrome 14则弹出“undefined”。

虽然currentStyle无法适用于所有浏览器，但是可以根据以上测试的结果来区分开支持、不支持的浏览器，然后再找到兼容的写法。

其实在FF浏览器中我们可以使用getComputedStyle(obj,false)来达到与IE下currentStyle相同的效果。

getComputedStyle(obj,false)：在FF新版本中只需要第一个参数，即操作对象，第二个参数写“false”也是大家通用的写法，目的是为了兼容老版本的火狐浏览器。

以下是兼容写法
```
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
    <style>
        #div{
            width: 200px;
            height: 200px;
            background: red;
        }
    </style>
</head>
<body>
    <input type="button" value="样式" id="btn">
    <div id="div"></div>
    <script>
        function css(obj, attr, value) {
            if (arguments.length === 2) {
                if (obj.currentStyle) {
                    return obj.currentStyle[attr];
                } else {
                    return getComputedStyle(obj, false)[attr];
                }

            } else if(arguments.length === 3){
                obj.style[attr] = value;
            }
        }
        window.onload = function (){
            var oBtn = document.getElementById("btn");
            var oDiv = document.getElementById("div");

            oBtn.onclick = function () {
                css(oDiv, 'background', 'green');
                console.log(css(oDiv, 'width'));
                // console.log(getComputedStyle(oDiv, false).width);
            }
        }
    </script>
</body>
</html>
```
```
不支持currentStyle的三款浏览器(FF、chrome、safari)，都是支持getComputedStyle的。
```
```
<script>
        // 哪个元素
        // 哪个样式
        function getStyle(obj, attr) {
            var style;
            if (obj.currentStyle) {
                style = obj.currentStyle[attr];
            } else{
                style = getComputedStyle(obj, false)[attr];
            }
            return style;
        }
        window.onload = function (){
            var oDiv = document.getElementById("box");
            console.log(getStyle(oDiv, 'backgroundColor'));
        }

</script>
```
