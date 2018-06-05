##### attribute是HTML标签上的某个属性，比如我们常见的id、class、value和onclick等属性，以及一些自定义的属性，比如大家熟悉的data-*，甚至像myAttr这样的自定义属性。比如著作权归作者所有。
##### properties，其主要是JavaScript获取DOM对象上的属性值。而且它是作为JavaScript的基本对象。这个节点包括很多property，比如classList、className之类的著作权归作者所有。
##### 为了从语义上对其有所差异性的区分，把attribute称为HTML Attribute，译为特性，把property称为DOM Property，译为属性。
##### 在实际使用的时候，property通过.（或[]）来访问HTML标签元素上的标准的attribute，也可以通过其来重置其值；但对于自定义的attribute通过.符号获取的##### 值是undefined，不过可以通过.来重置它，需要注意的是，虽然重置了，但并不会修改HTML标签中自定义的attribute值，它只会存在JavaScript中。
##### 对于HTML标签元素中的attribute，不管是标准的，还是自定义的，都可以通过getAttribute来获取，通过setAttribute来重置，还可以使用removeAttribute来删除。
##### property 修改value值，只能同步到property中，不同步到 attribute中
##### attribute中 修改value值，能同步到property中，能同步到 attribute中
##### property和attribute获取的值都是attribute重置后的value值。但用户在input中输入新的值，property获取的是用户新输入的值，而attribute还是最初setAttribute设置的value值著作权归作者所有。
### 不同
##### attribute的value值只在初始化的时候跟property一样，使用getAttribute获取的值是初始化的值，如果没有设置则是空，除非使用setAttribute手动去改变，但这个改变也不会影响到property的值。property的value值是input实时输入的值，但该值的改变同样也不会影响attribute的value值。著作权归作者所有。
### 总结
##### property和attributies都是properties的子集，而每个attribute是attributies的子集。attribute指的是HTML的Attribute，可以理解为HTML的特性，它们可以自定义，可以在HTML标签元素上添加attribute或者使用setAttribute添加（这两者添加的方式不一样，但结果一样）。大多数情况之下，HTML标签添加的都是##### attribute属性，property则是使用.符号进行更改。通常来讲，更自以为是相互影响（但也有不一样的地方，比如input的value）。另外，当添加的是非标准的属性时，property和attribute是不互通的。除此之外，一些特殊属性则需要特殊对待。

##### 在实际应用当中，大部分DOM操作都是使用properties来完成。但有些情形之下，使用attributes更为适合，比如：在自定义HTML的attributes，因为它并不同步到DOM的property。还有就是访问内置HTML的attributes（设置的初始值），attribute不能从property同步过来，典型的就是前面向大家展示的input的value。


