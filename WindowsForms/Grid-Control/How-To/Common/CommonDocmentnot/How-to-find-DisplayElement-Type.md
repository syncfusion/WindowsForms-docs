---
layout: post
title: Find DisplayElement Type in WinForms GridGroupingControl | Syncfusion
description: Learn here all about how to find DisplayElement Type of Syncfusion Windows Forms GridGroupingControl and more.
platform: windowsforms
control: GridGrouping
documentation: ug
---

# How to find DisplayElement Type in Windows Forms GridGroupingControl

You can find the type of particular DisplayElement using the code below.

 
{% highlight c# %}

//Accesses the type of display element.
Console.WriteLine(this.gridGroupingControl1.Table.DisplayElements[rowIndex].Kind);
{% endhighlight  %}

{% highlight vb %}

'Accesses the type of display element.
Console.WriteLine(Me.gridGroupingControl1.Table.DisplayElements(rowIndex).Kind)
{% endhighlight  %}