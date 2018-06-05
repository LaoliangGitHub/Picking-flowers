##### attribute是HTML标签上的某个属性，比如我们常见的id、class、value和onclick等属性，以及一些自定义的属性，比如大家熟悉的data-*，甚至像myAttr这样的自定义属性。比如著作权归作者所有。
##### properties，其主要是JavaScript获取DOM对象上的属性值。而且它是作为JavaScript的基本对象。这个节点包括很多property，比如classList、className之类的著作权归作者所有。
##### 为了从语义上对其有所差异性的区分，把attribute称为HTML Attribute，译为特性，把property称为DOM Property，译为属性。
##### 在实际使用的时候，property通过.（或[]）来访问HTML标签元素上的标准的attribute，也可以通过其来重置其值；但对于自定义的attribute通过.符号获取的##### 值是undefined，不过可以通过.来重置它，需要注意的是，虽然重置了，但并不会修改HTML标签中自定义的attribute值，它只会存在JavaScript中。
##### 对于HTML标签元素中的attribute，不管是标准的，还是自定义的，都可以通过getAttribute来获取，通过setAttribute来重置，还可以使用removeAttribute来删除。

