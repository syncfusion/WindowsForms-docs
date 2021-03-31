---
layout: post
title: Filtering support | WindowsForms | Syncfusion
description: Learn about filtering support in Syncfusion Windows Forms  MultiColumnTreeView control and more details.
platform: WindowsForms
control: MultiColumnTreeView
documentation: ug
---

# Filtering in MulticolumnTreeView

Filtering is the process of retrieving the values from a collection that satisfies the specified condition.

## FilterLevel

You can filter the nodes based on level using the [FilterLevel](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Windows.Forms.Tools.MultiColumnTreeView.MultiColumnTreeView.html#Syncfusion_Windows_Forms_Tools_MultiColumnTreeView_MultiColumnTreeView_FilterLevel)

{% tabs %}

{% highlight c# %}

this.multiColumnTreeView1.FilterLevel = FilterLevel.All;

{% endhighlight %}

{% highlight VB %}

Me.multiColumnTreeView1.FilterLevel = FilterLevel.All

{% endhighlight %}

{% endtabs %}

* Root - Filter will be applied only to root nodes in MultiColumnTreeView.

* All - Filter will be applied to all the nodes in MultiColumnTreeView.

* Extended - Filter will be applied to all the nodes. If a node matches the filter condition, its all ancestors will be displayed even though the parent node does not match the filter condition.

**Root**

Filter will be applied only to root nodes in MultiColumnTreeView. All other nodes will be invisible in view.

**All**

Filter will be applied to all the nodes in MultiColumnTreeView. If a parent node does not match the filter condition, filter will not be applied for child nodes. Else, filter will be applied to its child nodes also.

**Extended**

Filter will be applied to all the nodes. If a node matches the filter condition, its all ancestors will also be displayed even though the parent node does not match the filter condition.

N> You can change the `FilterLevel` at run time.

## Apply filter

Filtering can be achieved by setting the [Filter](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Windows.Forms.Tools.MultiColumnTreeView.MultiColumnTreeView.html#Syncfusion_Windows_Forms_Tools_MultiColumnTreeView_MultiColumnTreeView_Filter) delegate and calling the [RefreshFilter](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Windows.Forms.Tools.MultiColumnTreeView.MultiColumnTreeView.html#Syncfusion_Windows_Forms_Tools_MultiColumnTreeView_MultiColumnTreeView_RefreshFilter) method.

{% tabs %}

{% highlight C# %}

 public bool FilterNodes(object o)
 {
    var nodeadv = o as TreeNodeAdv;
    int value = int.Parse(nodeadv.SubItems[2].Text.ToString());
    if (value > 23000)
      return true;
    return false;
 }

  private void button1_Click(object sender, EventArgs e)
  {
    if (multiColumnTreeView1 != null)
      {
        multiColumnTreeView1.Filter = FilterNodes;
        multiColumnTreeView1.RefreshFilter();
      }
  }

 {% endhighlight %}      

 {% highlight VB %}

 Public Function FilterNodes(ByVal o As Object) As Boolean
    Dim nodeadv = TryCast(o, TreeNodeAdv)
    Dim value As Integer = Integer.Parse(nodeadv.SubItems(2).Text.ToString())
    If value > 23000 Then Return True
    Return False
End Function 

Private Sub button2_Click(ByVal sender As Object, ByVal e As EventArgs)
    If multiColumnTreeView1 IsNot Nothing Then
        multiColumnTreeView1.Filter = Nothing
        multiColumnTreeView1.RefreshFilter()
    End If
End Sub

{% endhighlight %}

{% endtabs %}

Here, `FilterNodes` delegate filters the node based on Salary. `FilterNodes` delegate is assigned to  [Filter](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Windows.Forms.Tools.MultiColumnTreeView.MultiColumnTreeView.html#Syncfusion_Windows_Forms_Tools_MultiColumnTreeView_MultiColumnTreeView_Filter) predicate to filter the nodes. After that, [RefreshFilter](https://help.syncfusion.com/cr/windowsforms/Syncfusion.Windows.Forms.Tools.MultiColumnTreeView.MultiColumnTreeView.html#Syncfusion_Windows_Forms_Tools_MultiColumnTreeView_MultiColumnTreeView_RefreshFilter) method is called to refresh the nodes. If the node satisfies the filter conditions, true will be returned. Else false will be returned.

![Filtering in MultiColumnTreeView](Filtering_images/Filtering.png)

## Clear filter

You can clear the filters applied in nodes by setting the `Filter` delegate to null and calling the `RefreshFilter` method.

{% tabs %}
{% highlight c# %}

multiColumnTreeView1.Filter = null;
multiColumnTreeView1.RefreshFilter();

{% endhighlight %}

{% highlight VB %}

multiColumnTreeView1.Filter = Nothing
multiColumnTreeView1.RefreshFilter()

{% endhighlight %}
{% endtabs %}

You can download the sample from [here](https://github.com/SyncfusionExamples/Filtering-support-in-MultiColumnTreeView).