>>>html部分
```
<iframe name="container_ifranme" id="iframeId" scrolling="no" frameborder="no" border="0" src="home.html" onLoad="iFrameHeight()" ></iframe>
```
>>>js部分
```
<script>
	//获取iframe子页面内容高度给iframe动态设置高度
	function iFrameHeight() {
	var ifm= document.getElementById("iframeId");
		var subWeb = document.frames ? document.frames["iframeId"].document : ifm.contentDocument;
		if(ifm != null && subWeb != null) {
			ifm.style.height = 'auto';//关键这一句，先取消掉之前iframe设置的高度
			ifm.style.height = subWeb.body.scrollHeight+'px';
		}
	};

```
