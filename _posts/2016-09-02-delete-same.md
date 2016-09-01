---
layout: post
title:  "数组去重"
date:   2016-09-02 00:30:00
categories: JavaScript Array
---

将数组中所有相同的数前面的都去掉，只留下最后一个，位置不变，最后使数组不含重复的数字

{% highlight javascript %}

var arr = [3,2,4,5,3,2,7,3,6,3,9,2,1];
function deleSame(arr){
    var temp = [];
    for(var i=arr.length-1;i>=0;i--){
        var n = arr[i];
        if(temp.indexOf(n)>=0){
          arr[i] = undefined;
        }else{
          temp.push(n);
        }
    }
    return arr;
}
deleSame(arr);

{% endhighlight %}
