---
layout: post
title:  "快速排序"
date:   2016-08-24 23:18:00
categories: JavaScript Sort Quick
---

基本思想是：通过一趟排序将要排序的数据分割成独立的两部分，其中一部分的所有数据都比另外一部分的所有数据都要小，然后再按此方法对这两部分数据分别进行快速排序，整个排序过程可以递归进行，以此达到整个数据变成有序序列。

{% highlight javascript %}
function quickSort(array){
    function sort(prev, numsize){
        var nonius = prev;
        var j = numsize -1;
        var flag = array[prev];
        if ((numsize - prev) > 1) {
            while(nonius < j){
                for(; nonius < j; j--){
                    if (array[j] < flag) {
                        array[nonius++] = array[j];　//a[i] = a[j]; i += 1;
                        break;
                    };
                }
                for( ; nonius < j; nonius++){
                    if (array[nonius] > flag){
                        array[j--] = array[nonius];
                        break;
                    }
                }
            }
            array[nonius] = flag;
            sort(0, nonius);
            sort(nonius + 1, numsize);
        }
    }
    sort(0, array.length);
    return array;
}
{% endhighlight %}

更多内容请参见[百度百科][baidu-baike];

[baidu-baike]: http://baike.baidu.com/link?url=gX2RHpMcBEfx7qwEYGjFHurJmT2zc6GKPEXI29uuXhno4JGc2Gv8lp79tmjDMZz_LoG3WaM-LTTQkhY5_p9flcfWCIvzXAr8KJdgK00-XktEQdMOa_n8h2wp10sMTNL_6pp2REuLWksd-yEBmcKX1LrO_KWS6lPafuLDYWPhuRzsXEbLBE8tCwuBXVD2vO3G
