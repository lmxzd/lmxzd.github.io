# 使用

1. 使用_layouts下已有布局, html格式, 一般使用page即可.

  1. blog 带分页器(根据categories分类), 侧边栏和广告
  2. compress 最底层布局
  3. default 带头,尾等信息, 在compress之上, 也是底层的布局
  4. frontpage 首页布局, 可以放多个widget
  5. page/page-fullwidth布局, 一般发布就用这个
  6. redirect 重定向布局
  7. video 视频布局

2. 博客就写在post下面, 作为发布模块, 归档

3. page下是分级菜单. 后续

4. _data下有快速调整页面的元数据

  5. 作者
  6. 映射
  7. 网址
  8. 社交媒体等

9. 页面有各种格式, 支持以下

  1. 带有左/右侧边栏
  2. 全页

10. 页面头格式, 在post design中有示例, 使用header来标记

  - 带图带logo 

  ```yml
  header:
      image: header_unsplash_2-970x.jpg
      pattern: pattern_concrete.jpg
      caption: This is a caption for the header image with link
      caption_url: https://unsplash.com/
  ```

  - 带全图带logo

  ```yml
  header:
      image_fullwidth: "unsplash_brooklyn-bridge_header.jpg"
      caption: This is a caption for the header image with link
      caption_url: https://unsplash.com/
  ```

  - 只带logo 默认模式, 不需要带header
  - 带图和自定义文字

  ```yml
  header:
      title: header with text
      background-color: "#EFC94C;"
  #    pattern: pattern_concrete.jpg
      image_fullwidth: unsplash_brooklyn-bridge_header.jpg
      caption: This is a caption for the header image with link
      caption_url: https://unsplash.com/
  ```

  - 无头有图

  ```yml
  header: no
  image:
      title: unsplash_eagle.jpg
      caption: This is a caption for the header image with link
      caption_url: https://unsplash.com/
  ```

  - 无头

  ```yml
  header: no
  ```

11. 可以分类, 并且在文档末尾使用include的tag标签来包含这些分类.

12. 可以通过此代码将md的目录给出来.

13. 如果想加js, 可以在布局中加入判断(Liquid语法),如果页面元数据有什么时, 加载以下js.

14. 左目录

	```html
	<div class="medium-4 medium-pull-0 columns" markdown="1">
	<div id = "wheel" class="panel radius" markdown="1">
	**目录**
	{: #toc }
	*  TOC
	{:toc}
	</div>
	</div><!-- /.medium-4.columns -->
	<div class="medium-8 medium-push-0 columns" markdown="1">
	    ** 内容**
	</div>    
	```

15. 右目录

	```html
	<div class="medium-4 medium-push-9 columns" markdown="1">
	<div id = "wheel" class="panel radius" markdown="1">
	**目录**
	{: #toc }
	*  TOC
	{:toc}
	</div>
	</div><!-- /.medium-4.columns -->
	<div class="medium-8 medium-push-0 columns" markdown="1">
	    ** 内容**
	</div>  
	```

16. page布局可以获取tags，文件名的时间前缀作为末尾。且有上一个下一个。归档于categories对应的下面。

17. 评论后续使用下gittalk, 在md中include html试试可以不可以把评论带过来.(后续做)

18. 默认post下是归档内容. 但是可以通过修改archive.html修改for循环对象.

19. permalink代表了当前页面实际的url,用于项目中路由使用.

20. \_config.yml中的default. path是下指定的文件夹即同级目录下的文件夹. type字段的作用

	1. `posts`: 仅适用于博客文章（默认情况下位于 `_posts` 目录中）。可以看成是规定.
	2. `pages`: 仅适用于普通页面（通常位于项目根目录或其他自定义目录中）。
	3. `all`: 适用于所有类型的内容（包括文章和页面）。

21. 通过pages目录下作为入口内容, 根据标签分组.

22. **post下为发布内容和归档内容.归档可以加上标签的归档, 然后去循环标签. 达到按分类归档的目的**

23. **分类的跳转 跳到各个主题的首页, 各个主题再根据标签来决定上一篇, 下一篇, 各个分类里根据时间排序, 最新的放到上面.** 

24. 首页就放最新的文章.

25. gallery是放图片的, 以后会摄影的话放一点也可以

26. include 博客时, 按时间排序, 时间早的在后面. 原理使用的是list-posts文件, 可以使用分页方式. 然后利用标签去获取特定的博客.

27. 可以使用include组装网页. 

28. **目前的目录样式如下:**

	1. 首页给最新的文章
	2. 首页的每个上面栏都可以点击, 跳转到具体主体的父页面, 父页面使用frontpage-xxx布局
	3. 首页上面栏的子主题就直接跳转到这个主题的固定文章. 在最下面包含这些子主题的所有内容.
	4. 分类里包含主题内的所有内容, 主体本身不可点击, 但下方有文章. 点击更多, 跳转到归档页面.
	5. 具体文章中带有侧边目录, 最下方带有带有具体的category, 展示具体的category文章 或者直接用blog_type. 如果用category, 这注意, 把entries调超大, 直接全页展示. blog_type的话, 可以特定页数.

29. 通过在`language.yml`和`_include`下的`html`配合, 可以快速定义按钮的汉字

30. show meta代表的是最下面的上一页, 下一页和归档. 这个暂时删掉, 后面看看怎么做到只在当前blog_type下上下, 应该也是类似于mylist的这种改法. 暂时不要元数据.

31. category作为子主题(比如说java base), tag作为分类(可以归于一些思想的, 目的就是交叉分类. 多种分组.)

32. 这个还是不好用, 后续还是用vue和java后端来实现. 做一个发布功能, 自动上传到服务端. 目前先这样.

33. 

# 原理

1. krmarkdown可以定义html和md的元数据, 进而达到近似组合的效果, 以此来复用.
2. 



# 后续任务

1. 明天将主页上的东西弄好, 剩余的英文改为汉语
2. 后续逐步发布post文章.