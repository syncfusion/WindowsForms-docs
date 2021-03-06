---
layout: post
title: How to select multiple items in the dropdown | Syncfusion
description: Learn about How to Select Multiple Items in the Dropdown support in Syncfusion Windows Forms ComboBoxAdv(Classic) control and more details.
platform: WindowsForms
control: ComboBoxAdv
documentation: ug
---

# How to select multiple items in the dropdown

This page explains How to Select Multiple Items in the Dropdown and more details.

## How to Select Multiple Items in the Dropdown

In order to perform multiple selection, you can use the ComboboxAdv or MultiColumnComboBox controls, that contains a normal ListBox that allows you to select multiple items, internally.

{% tabs %}
{% highlight c# %}

//To select multiple items in ComboBoxAdv
this.comboBoxAdv1.ListBox.SelectionMode = SelectionMode.MultiExtended;
this.multiColumnComboBox1.ListBox.SelectionMode = SelectionMode.MultiExtended;

{% endhighlight %}

{% highlight vb %}

'To select multiple items in ComboBoxAdv
Me.comboBoxAdv1.ListBox.SelectionMode = SelectionMode.MultiExtended
Me.multiColumnComboBox1.ListBox.SelectionMode = SelectionMode.MultiExtended

{% endhighlight %}
{% endtabs %}
