---
layout: post
title:  "驼峰转换"
date:   2016-08-25 11:32:00
categories: JavaScript tool hump
---

##### 普通循环算法

```javascript
var str="border-bottom-color";
    function Change(str){
        var arr=str.split("-");
        for(var i=1;i<arr.length;i++){
            arr[i]=arr[i].charAt(0).toUpperCase()+arr[i].substring(1);
        }
        str=arr.join("");
        return str;
    }
    console.log(Change(str));//borderBottomColor
```

##### 正则替换

```javascript
var s = "my-name-is-laolu";
function hump(str){
  return str.replace(/\-[a-z]/gi,function(n){
    return n.substr(1).toLocaleUpperCase();
  })
}
console.log( hump(s) ); // myNameIsLaolu
```

