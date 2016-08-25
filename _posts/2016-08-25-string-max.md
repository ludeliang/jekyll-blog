---
layout: post
title:  "查找字符串中出现次数最多的字符和次数"
date:   2016-08-25 14:30:00
categories: JavaScript String Max
---

例如：sdddrtkjsfkasjdddj中出现最多的字符是d,出现了6次

```javascript
     var str="sdddrtkjsfkkkasjdddj";
        var max=0;
        var char;
        function Search(str){
            var json={};
            for(var i=0;i<str.length;i++){
                if(!json[str[i]]){
                    json[str[i]]=str[i];
                }
                else{
                    json[str[i]]+=str[i];
                }
            }

            for(var i=0;i<str.length;i++){
                if(json[str[i]].length>max){
                    max=json[str[i]].length;
                    char=str[i];
                }
            }
            console.log("出现次数最多的字符是"+char+",出现了"+max+"次")
        }
        Search(str);
```

##### 老卢改进一下
```javascript

    var str="sdddrtkjksfkkkasjdddj";
    var arr= str.split("");
        arr.sort();
    var max = 0,count = 0;
    var char = "",mark = "";
    while(arr.length){
        var temp = arr.pop();
        if(mark==temp){
            count++;
        }else{
            count = 1;
            mark = temp;
        }
        if(count>max){
            char = temp;
            max = count;
        }else if(count==max){
            char += "," + temp;
        }
    }
    console.log("出现次数最多的字符是"+char+",出现了"+max+"次")

```