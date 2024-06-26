---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header_unsplash_12.jpg
widget1:
  title: "重构"
  url: 'https://lmxzd.github.io/lmxzd/architecture/restructure/'
  image: widget-github-303x182.jpg
  text: '重构的唯一目标是提高生产效率。这篇文章根据《重构：改善既有代码的设计（第二版）》并结合日常的项目经验介绍重构的必要性。'
widget2:
  title: "设计模式遵循的原则"
  url: 'http://lmxzd.github.io/lmxzd/architecture/principlesOfDesignPatterns/'
  image: gallery-example-1.jpg
  text: '设计模式描述了面向对象软件设计中经常遇到的问题，以及解决这些问题的通用解决方案。而面向对象的设计原则是更深层次的抽象。这篇文章将会介绍这些设计原则，并以一些设计模式为例介绍这些原则在设计模式中的使用。'
widget3:
  title: "Java 运行jar的方式"
  url: 'http://lmxzd.github.io/lmxzd/java/jar-run-type/'
  image: gallery-example-1.jpg
  text: '学习'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
# callforaction:
#   url: https://tinyletter.com/feeling-responsive
#   text: Inform me about new updates and features ›
#   style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#

homepage: true
---

