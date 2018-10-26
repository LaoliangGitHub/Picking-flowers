#### 基本上，做PC页面项目里都有一个Panel或者Dialog组件，就是弹框什么的。其中，下面会有“确定”，“取消”按钮
#### 然后，具体很奇怪的，有几个Dialog，设计希望这两个按钮顺序是相反的。
```
  <p class="rtl"><img src="mm1.jpg"> <img src="mm2.jpg"></p>
  <p class="rtl"><span>span1</span> <span>span2</span></p>
  <p>
    <button>确定</button> <button>取消</button>
    <a href="javascript:" class="btn">确定</a> <a href="javascript:" class="btn">取消</a>
  </p>
```
![确定在左边](https://github.com/wy7365596/Picking-flowers/blob/master/css/images/directionA.png)
##### 给p标签加上样式 direction: rtl; 
![确定在右边](https://github.com/wy7365596/Picking-flowers/blob/master/css/images/directionB.png)


