---
layout: post
title: About Essential Studio Windows Forms Licensing | Syncfusion
description: Learn here about Syncfusion Essential Studio Windows Forms license key, how to generate the license key, how to register the license key, and more details.
platform: WindowsForms
control: Essential Studio
documentation: ug
---


# License Key Registration

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.

### Windows Forms

You can register the licensing code in static void main method before calling **Application.Run()** method in C#. In Visual Basic, register the licensing code in **Application.designer.vb** file constructor.

{% tabs %}
{% highlight c# %}
static void Main()
{
	//Register Syncfusion license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	
    Application.EnableVisualStyles();
    Application.SetCompatibleTextRenderingDefault(false);
    Application.Run(new Form1());
}
{% endhighlight %}

{% highlight vb %}
Public Sub New()
		MyBase.New(Global.Microsoft.VisualBasic.ApplicationServices.AuthenticationMode.Windows)
		'Register Syncfusion License
		Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
		Me.IsSingleInstance = False
		Me.EnableVisualStyles = True
		Me.SaveMySettingsOnExit = True
		Me.ShutdownStyle = Global.Microsoft.VisualBasic.ApplicationServices.ShutdownMode.AfterMainFormCloses
End Sub
{% endhighlight %}

{% endtabs %}