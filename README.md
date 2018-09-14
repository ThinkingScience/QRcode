# QRcode.js

## 1. github地址:
`## 1. github地址:
`https://github.com/davidshimjs/qrcodejs``

## 2. 什么是QRcode?
`QRCode.js 是一个用于生成二维码的 JavaScript 库。主要是通过获取 DOM 的标签,再通过 HTML5 Canvas 绘制而成,不依赖任何库。`

### 2.1 基本用法:
```
<div id="qrcode"></div>
<script type="text/javascript">
new QRCode(document.getElementById("qrcode"), "http://www.runoob.com");  // 设置要生成二维码的链接
</script>
```
或者使用一些可选参数设置：
```
var qrcode = new QRCode("test", {
    text: "http://www.runoob.com",
    width: 128,
    height: 128,
    colorDark : "#000000",
    colorLight : "#ffffff",
    correctLevel : QRCode.CorrectLevel.H
});
```
同样我们可以使用以下方法：
```
qrcode.clear(); // 清除代码
qrcode.makeCode("http://www.w3cschool.cc"); // 生成另外一个二维码
```
### 2.2 浏览器支持:
`支持该库的浏览器有：IE6~10, Chrome, Firefox, Safari, Opera, Mobile Safari, Android, Windows Mobile, 等。`

### 2.3 实例代码:
HTML 代码:
```
<input id="text" type="text" value="http://www.runoob.com" /><br />
<div id="qrcode"></div>
```
CSS 代码:
```
#qrcode {
width:160px;
  height:160px;
  margin-top:15px;
} 
```
JavaScript 代码:
```
var qrcode = new QRCode("qrcode");

function makeCode () {      
    var elText = document.getElementById("text");
    
    if (!elText.value) {
        alert("Input a text");
        elText.focus();
        return;
    }
    
    qrcode.makeCode(elText.value);
}

makeCode();

$("#text").
on("blur", function () {
    makeCode();
}).
on("keydown", function (e) {
    if (e.keyCode == 13) {
        makeCode();
    }
});
```

区别:
	1. 使用简单方式,生成的二维码宽高为256*256,给div设置宽高无效;
	2. 使用设置参数方式,直接在option中设置宽高;
