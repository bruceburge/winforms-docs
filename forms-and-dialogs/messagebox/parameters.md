---
title: Parameters
page_title: Parameters
description: Parameters
slug: forms-and-dialogs-messagebox-parameters
tags: parameters
published: True
position: 1
---

# Parameters



## SetThemeName method

You can easily set the ThemeName of the RadMessageBox by calling the SetThemeName parameter,
          passing the theme name string:
        

#### __[C#] Setting a theme in RadMessageBox__

{{source=..\SamplesCS\Forms and Dialogs\MessageBox1.cs region=SetThemeName}}
	            RadMessageBox.SetThemeName("Desert");
	{{endregion}}



#### __[VB.NET] Setting a theme in RadMessageBox__

{{source=..\SamplesVB\Forms and Dialogs\MessageBox1.vb region=SetThemeName}}
	        RadMessageBox.SetThemeName("Desert")
	{{endregion}}



## Show method

The Show method displays a RadMessageBox. It returns a DialogResult value and has a couple of overloads to suit to your needs.
        For a list of all methods see the API Reference section. Show method could accept the following parameters:

* __Parent__ - An implementation of System.Windows.Forms.IWin32Window that will own the RadMessageBox.
            

* __Text__ - The text to display in the RadMessageBox.
            

* __Caption__ - The text to display in the title bar of the RadMessageBox.
            

* __Buttons__ - One of the MessageBoxButtons enumeration values that specifies which buttons to display in the message box:
            

* AbortRetryIgnore

* OK

* OKCancel

* RetryCancel

* YesNo

* YesNoCancel

* __Icon__ - One of the RadMessageIcon enumeration values that
              specifies which icon to display in the message box or a custom Bitmap icon that will be displayed:
            

* RadMessageIcon.None

* RadMessageIcon.Info

* RadMessageIcon.Question

* RadMessageIcon.Exclamation

* RadMessageIcon.Error

* __defaultBtn__ - One of the MessageBoxDefaultButton enumeration values
              the specifies the default button for the message box:
            

* MessageBoxDefaultButton.Button1

* MessageBoxDefaultButton.Button2

* MessageBoxDefaultButton.Button2

* __Rtl__ - RightToLeft settings:
            

* RightToLeft.No

* RightToLeft.Yes

* RightToLeft.Inherit

## Details Section

As of Q2 2014 __RadMessageBox__ supports details section. This section can be shown by just specifying the details text in the 
          Show method parameters:
        

#### __[C#]__

{{source=..\SamplesCS\Forms and Dialogs\MessageBox1.cs region=details}}
	            RadMessageBox.Show("Message", "Caption Text", MessageBoxButtons.AbortRetryIgnore, "Details Text");
	{{endregion}}



#### __[VB.NET]__

{{source=..\SamplesVB\Forms and Dialogs\MessageBox1.vb region=details}}
	        RadMessageBox.Show("Message", "Caption Text", MessageBoxButtons.AbortRetryIgnore, "Details Text")
	{{endregion}}



The result looks like this:
        ![forms-and-dialogs-messagebox-parameters 001](images/forms-and-dialogs-messagebox-parameters001.png)