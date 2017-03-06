# 这篇文章主要介绍了通过javascript控制input只允许输入的各种指定内容,需要的朋友可以参考下
## 1、只允许输入数字
```javascript
<input name="username" type="text" onkeyup="value=this.value.replace(/\D+/g,'')">
```
## 2、只允许输入英文字母、数字和下划线(以下二种方法实现)
```javascript
<input name="username" type="text" style="ime-mode:disabled">
<input name="username" type="text" onkeyup="value=value.replace(/[^\w\.\/]/ig,'')">
```
## 3、只允许输入英文字母、数字和=@#
```javascript
<input name="username" type="text" onkeyup="value=value.replace(/[^\w=@#]|_/ig,'')">
```
## 4、只允许输入汉字
```javascript
<input name="username" type="text" onkeyup="value=value.replace(/[^\u4E00-\u9FA5]/g,'')">
```
-
### 只能输入数字："^[0-9]*$"。
### 只能输入n位的数字："^\d{n}$"。
### 只能输入至少n位的数字："^\d{n,}$"。
-
### 只能输入m~n位的数字：。"^\d{m,n}$"
### 只能输入零和非零开头的数字："^(0|[1-9][0-9]*)$"。
-
### 只能输入有两位小数的正实数："^[0-9]+(.[0-9]{2})?$"。
-
### 只能输入有1~3位小数的正实数："^[0-9]+(.[0-9]{1,3})?$"。
### 只能输入非零的正整数："^\+?[1-9][0-9]*$"。
-
### 只能输入非零的负整数："^\-[1-9][]0-9"*$。
### 只能输入长度为3的字符："^.{3}$"。
-
### 只能输入由26个英文字母组成的字符串："^[A-Za-z]+$"。
### 只能输入由26个大写英文字母组成的字符串："^[A-Z]+$"。
-
### 只能输入由26个小写英文字母组成的字符串："^[a-z]+$"。
### 只能输入由数字和26个英文字母组成的字符串："^[A-Za-z0-9]+$"。
-
### 只能输入由数字、26个英文字母或者下划线组成的字符串："^\w+$"。
-
### 验证用户密码："^[a-zA-Z]\w{5,17}$"正确格式为：以字母开头，长度在6~18之间，只能包含字符、数字和下划线。
-
### 验证是否含有^%&',;=?$\"等字符："[^%&',;=?$\x22]+"。
-
### 只能输入汉字："^[\u4e00-\u9fa5]{0,}$"
-
### 只能输入数字和小数点，防粘贴：
-
```javascript
<input type=""text" onkeyup="value=value.replace(/[^0-9.]/g,''),dxfqlld();" onpaste="value=value.replace(/[^0-9.]/g,'')" oncontextmenu="value=value.replace(/[^0-9.]/g,'')" />
```
