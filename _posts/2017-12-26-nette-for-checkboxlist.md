---
title: Nette框架使用checkboxlist指南
category: PHP
tags: [nette,php,framework,checkbox]
description: Nette框架使用checkboxlist指南
---

## 先在presenter中增加form组件

{% highlight php linenos %}
function createComponentSignInForm()
{
    $form = new Form;
    $form->addText('user')->setRequired();
    $form->addPassword('password')->setRequired();
    //此处是添加列表，参数为：控件name，显示的label, 数组：array('k'=>'v')
    $form->addCheckboxList('cbl','checkboxlist列表', array('f'=>'男','m'=>'女'));
    
    $form->addSubmit('send');
    return $form;
}
{% endhighlight %}

然后在相关layout视图文件中引用：

{% highlight html linenos %}
{foreach $form[chk]->items as $key => $label}
    <label n:name="gender:$key"><input n:name="gender:$key"> {$label}</label>
{/foreach}
{% endhighlight %}
