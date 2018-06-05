
### HTMLElement.style.cssText  eg $0.style.cssText = 'color:#f36; font-size: 2rem;padding: 10px'
> $0.style.cssText += 'color:#f36; font-size: 2rem;padding: 10px'
>> 不填‘+=’会直接覆盖掉

### 通过className和classList控制样式
> 使用className给指定的元素删除一个类名，相对来说比较麻烦一点。比如上例，咱们使用addClass()函数之后，通过$0.className可以读取出当前元素$0的class的值为new jhp primary

> 通过classList来添加和删除类等 
>> elem.classList.add()： 添加类名
>> elem.classList.remove()：删除类名
>. elem.classList.toggle()：切换类名，如果改类名存在将会删除该类名，如果不存在将会添加该类名
