---
title: Hudson, Jenkins & Bamboo
toc: false
---

Checkstyle has `xml` report option that can be used to integrate with Hudson, Jenkins and Bamboo.

If you want to style the generated XML you can set XSLT style for the XML generated. See the sample below.

```
haxelib run checkstyle -s src -c config.json -p report.xml -x report.xsl
```

### Sample Trend Chart

![img](images/hudson.png)