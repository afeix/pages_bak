---
layout: post
title: JavaScript按中文姓名排序
description: JavaScript对姓名排序
category: JavaScript
tags: [排序]
---

对返回的JSON数据，按照本地的方式排序，比如姓名按音序排序。

{% highlight javascript linenows %}
/**
 * 这段代码是返回JSON数据，并生成一个select，按照姓名填充option
 * 使用localComare()函数，a.xm.localeCompare(b.xm)，用在sort()
 * 自定义的排序方式中。
 */
$.getJSON(base_url + '/cx/getbjxs/'+bj, function(data) {
	var items = ['<select id="xs" name="xs"><option value="0">请选择</option>'];
	data.sort(function(a,b){
		return a.xm.localeCompare(b.xm);//这是关键的排序
	});
	$.each(data, function(key, val) {
		items.push('<option value="'+ val['sfzh'] +'">' + val['xm'] + '</option>');
	});
	items.push('</select>');
	$('#cxs').html(items.join(''));
});
{% endhighlight %}
