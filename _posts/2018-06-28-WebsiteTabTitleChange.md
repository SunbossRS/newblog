---
layout: post
title: '如何在切换网站后改变标题'
tags: jekyll
categories: dump
cover: 'https://coding.net/u/SunbossRS/p/GotBlogDowner/git/raw/master/img/WebsiteShow/01.png'
---

funnytitle~

---

打开你的网站目录，打开你网站的一个网站服务文件，要是html的。  
copy这行代码
```html
<script>
 /**
  *Funny Title
 */
  var title=document.title;
  var hiddenProperty = 'hidden' in document ? 'hidden' :
      'webkitHidden' in document ? 'webkitHidden' :
          'mozHidden' in document ? 'mozHidden' :
              null;
  var visibilityChangeEvent = hiddenProperty.replace(/hidden/i, 'visibilitychange');
  var onVisibilityChange = function(){
      if (!document[hiddenProperty]) {
          document.title = title;
      }else{
          document.title = "你找不到我啦! -" + title;
      }
  }
  document.addEventListener(visibilityChangeEvent, onVisibilityChange);
</script>
``` 
其中`document.title = "你找不到我啦! -" + title;`是在tab切换后显示的标题。你可以自己修改。
保存再上传，看看你的网站页尾发生了什么？  
![pic](https://coding.net/u/SunbossRS/p/GotBlogDowner/git/raw/master/img/WebsiteShow/02.png)
