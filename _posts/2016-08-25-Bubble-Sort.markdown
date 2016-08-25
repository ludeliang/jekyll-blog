---
layout: post
title:  "冒泡排序"
date:   2016-08-25 10:06:00
categories: JavaScript Sort Bubble
---

冒泡排序算法的运作如下：（从后往前）
比较相邻的元素。如果第一个比第二个大，就交换他们两个。
对每一对相邻元素作同样的工作，从开始第一对到结尾的最后一对。在这一点，最后的元素应该会是最大的数。
针对所有的元素重复以上的步骤，除了最后一个。
持续每次对越来越少的元素重复上面的步骤，直到没有任何一对数字需要比较:

```javascript
function bubbleSort(arr) {
    var i = arr.length, j;
    var tempExchangVal;
    while (i > 0) {
        for (j = 0; j < i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                tempExchangVal = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = tempExchangVal;
            }
        }
        i--;
    }
    return arr;
}

var arr = [3, 2, 4, 9, 1, 5, 7, 6, 8];
var arrSorted = bubbleSort(arr);
console.log(arrSorted);
alert(arrSorted);
```

更多内容请参见[百度百科][baidu-baike];

[baidu-baike]: http://baike.baidu.com/link?url=fzmiSmCLGlsLKEc6V5xNk0cX20x48af1zCRzf1XEo8VcHpJHM9xQjohKlE6ULVoXEgd4zdj24c3heBEjcbM3WK
