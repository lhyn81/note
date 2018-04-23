---
title: Web Note
tags: Web, Javascript, CSS, Html
---

[toc]

----------
## Html
## Javascript
### onclick跳转的代码
```
onclick="Go('hk_money.php');return false"
onclick="javascript:window.location.href='URL'"
onclick="location='URL'"
onclick="window.location.href='URL?id=11'"
onclick="window.open('https://www.alipay.com','_blank');" //在新页面打开
onclick="window.open('https://www.alipay.com','_self');"  //覆盖当前页面打开，不出弹出刷新提示哦！可以用这个做刷新功能！ 
```
### js注意事项
“”之间不要再出现 " ,要用 ' 代替。以下代码的wd就是例子，否则一直报错。

```
<a href="#" onclick="window.open('query?word=' + document.getElementsByName('wd')[0].value ,'_blank')">查 询</a>
```
### td的文字内容

```
document.getElementById ( "tdid" ).innerText
document.getElementById ( "tdid" ).textContent
$("#tdid").text(); （JQUERY）
tdElem.innerHTML;
$("#tdid").html();（JQUERY）
```
## CSS
## JQuery




