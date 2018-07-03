#### 我们需要将一串日期字符串转换为具体的Date格式的时候，往往需要用到new Date("xxxx")方法
> 兼容性有问题 
> 在具体使用的时候，可以通过一些字符串转换的方式，将日期字符串格式转换正确之后，再使用new Date()。
``` var date="2016-12-12 10:10:10";
date=date.replace(new RegExp(/-/gm) ,"/"); 　　//将所有的'-'转为'/'即可
Date d=new Date(date);
```
