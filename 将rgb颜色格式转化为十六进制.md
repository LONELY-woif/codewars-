## 题目要求

把 rgb 格式的颜色值 变为 十六进制（英文字母大写）

### 例子

    rgb(255, 255, 255) // returns FFFFFF
    rgb(255, 255, 300) // returns FFFFFF
    rgb(0,0,0) // returns 000000
    rgb(148, 0, 211) // returns 9400D3

### 我的想法

* 用 while 循环 遍历每一个参数 
* 判断参数是否在 0 ~ 255 之间 如果 <= 0 就让这个参数等于 ‘00’  如果 > 255 就让参数等于 255
* 然后把参数转化为十六进制 在把英文字母改为大写

### 我的代码

    function rgb(r, g, b){
   
  	  var num = arguments.length;
  	  var i = 0;
 	  var str = '';

      while (i < num) {
        arguments[i] > 255 && (arguments[i] = 255);
        arguments[i] <= 0 && (arguments[i] = '00');
  
        str += arguments[i].toString(16).toUpperCase();
        i ++; 
      }

      return str;
    }

### 大神代码

    function rgb(r, g, b){
      return [].map.call(arguments, function(arg) {
        return arg <= 0 ? '00' : arg > 255 ? 'FF' : arg.toString(16);
      }).join('').toUpperCase();
    }

### 学到的知识

大神代码中用到了 map() call() 和三目运算符判断方法，从中了解了这些方法的用法


从大神的代码中也学到了大神的解题思路 对我以后的解题思路将会有很大的帮助
