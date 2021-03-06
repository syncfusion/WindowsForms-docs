---
layout: post
title: How to display the AutoComplete popup programmatically, when a textbox is enabled with AutoComplete feature | WindowsForms | Syncfusion
description: How to display the AutoComplete popup programmatically, when a textbox is enabled with AutoComplete feature
platform: WindowsForms
control: Tools
documentation: ug
---

# How to display the AutoComplete popup programmatically, when a textbox is enabled with AutoComplete feature?

[AutoComplete popup](https://help.syncfusion.com/windowsforms/autocomplete/autocomplete-popup) can be displayed programmatically.

The following code demonstrates the same.

{% tabs %}

{% highlight C# %}

this.autoComplete1.AutoCompletePopup.ParentControl = this.textBox1;

this.autoComplete1.AutoCompletePopup.ShowPopup(Point.Empty);

{% endhighlight %}

{% highlight VB %}

Me.autoComplete1.AutoCompletePopup.ParentControl = Me.textBox1

Me.autoComplete1.AutoCompletePopup.ShowPopup(Point.Empty)

{% endhighlight %}

{% endtabs %}

![AutoComplete popup programmatically](FAQ_images/Faq_img1.jpg) 