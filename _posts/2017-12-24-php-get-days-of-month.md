---
layout: post
title: PHP计算当月天数
description: PHP计算当月天数
category: PHP
tags: [计算,天数]
---

当月天数

{% highlight php linenos %}
<?php
//计算当月天数
// $m 月份  $y 年份
cal_days_in_month(CAL_GREGORIAN, $m, $y);

?>
{% endhighlight %}
