---
layout: post
title: Format the Text in Windows Forms GridDataBoundGrid | Syncfusion
description: Learn about How to Format the Text support in Syncfusion Windows Forms GridDataBoundGrid(Classic) control and more details.
platform: windowsforms
control: DataBoundGrid
documentation: ug
---

# Format the Text in Windows Forms GridDataBoundGrid

This page explains How to Format the Text in Windows Forms and more details.

## How to Format the Text in Windows Forms

The purpose of QueryCellFormattedText is to take data, which is present in the Total Marks and convert it to Percentage for display. The SaveCellFormattedText takes the units that are entered by the user in Percentage and converts them to Total Marks so that they can be saved as Total Marks.

{% tabs %}
{% highlight c# %}

private void Model_QueryCellFormattedText(object sender, Syncfusion.Windows.Forms.Grid.GridCellTextEventArgs e)
{
   if(e.Style.CellValueType==typeof(double) && e.Style.Text.Length > 0)
   {
   
//Converts the cell value to percentage for display.
       double dVal = (double)e.Style.CellValue/500 *100; 
       e.Text = dVal.ToString("##.##"); 
       e.Handled = true;
   }
}
private void Model_SaveCellFormattedText(object sender, Syncfusion.Windows.Forms.Grid.GridCellTextEventArgs e)
{
   if(e.Style.CellValueType==typeof(double) && e.Style.Text.Length > 0)
   {

//Converts the Cell Value again from percentage to its original format.
       double dVal = double.Parse(e.Text)/100 *500;

//Saves the converted cell value.
       e.Style.CellValue = dVal; 
       e.Handled = true;
   }
}

{% endhighlight %}

{% highlight vb %}

Private Sub Model_QueryCellFormattedText(ByVal sender As Object, ByVal e As Syncfusion.Windows.Forms. 
Grid.GridCellTextEventArgs)
If e.Style.CellValueType Is GetType(Double) AndAlso e.Style.Text.Length > 0 Then

'Converts the cell value to percentage for display.
Dim dVal As Double = CDbl(e.Style.CellValue)/500 *100
e.Text = dVal.ToString("##.##")
e.Handled = True
End If
End Sub
Private Sub Model_SaveCellFormattedText(ByVal sender As Object, ByVal e As Syncfusion.Windows.Forms.Grid.GridCellTextEventArgs)
If e.Style.CellValueType Is GetType(Double) AndAlso e.Style.Text.Length > 0 Then

'Converts the Cell Value again from percentage to its original format.
Dim dVal As Double = Double.Parse(e.Text)/100 *500

'Saves the converted cell value.
e.Style.CellValue = dVal
e.Handled = True
End If
End Sub

{% endhighlight %}
{% endtabs %}
