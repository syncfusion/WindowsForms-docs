---
layout: post
title: Clipboard contents in Griddataboundgrid | Windows Forms | Syncfusion
description: Learn about How to Stop Errors Thrown When Pasting Larger Clipboard Contents in Windows Forms GridDataBoundGrid and more.
platform: windowsforms
control: DataBoundGrid
documentation: ug
---

# Clipboard contents in Grid data bound grid

This page explains How to Stop Errors Thrown when Pasting Larger Clipboard Contents in GridDataBoundGrid and more details.

## How to Stop Errors Thrown when Pasting Larger Clipboard Contents in GridDataBoundGrid

IndexOutOfRangeException is thrown when trying to paste clipboard contents that are greater than the number of columns and rows that are available to accommodate the contents. To stop the exception, a condition check at Model.PasteCellText handler will do good.

{% tabs %}
{% highlight c# %}

private void Model_PasteCellText(object sender, Syncfusion.Windows.Forms.Grid.GridPasteCellTextEventArgs e)
{

//Checks Whether the RowIndex crosses the upper bound.
     if(e.RowIndex >= this.gridDataBoundGrid1.Model.RowCount)
     {

//If row index falls beyond upper bound, Cancels and Aborts the Paste process.
         MessageBox.Show("There is no enough rows to paste the rest of the contents");
         e.Cancel = true;
         e.Abort = true;
     }
}

{% endhighlight %}

{% highlight vb %}
Private Sub Model_PasteCellText(ByVal sender As Object, ByVal e As Syncfusion.Windows.Forms.Grid.GridPasteCellTextEventArgs)

'Checks Whether the RowIndex crosses the upper bound.  
If e.RowIndex >= Me.gridDataBoundGrid1.Model.RowCount Then

'If row index falls beyond upper bound, Cancels and Aborts the Paste process.
MessageBox.Show("There is no enough rows to paste the rest of the contents")
e.Cancel = True
e.Abort = True
End If
End Sub

{% endhighlight %}
{% endtabs %}
