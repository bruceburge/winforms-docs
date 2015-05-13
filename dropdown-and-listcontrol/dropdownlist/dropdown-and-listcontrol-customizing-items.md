---
title: Customizing Items
page_title: Customizing Items
description: Customizing Items
slug: dropdown-and-listcontrol-dropdownlist-customizing-items
tags: customizing,items
published: True
position: 3
---

# Customizing Items



## Customizing drop down list items appearance

Items appearance in __RadDropDownList__ can be customized by
          making use of the __VisualListItemFormatting__ event. The
          following example, demonstrates how you can change the color of an item which
          is being selected
        

>By using this event to customize the items appearance, you should always provide an else clause,
            where you reset the appearance settings which you have introduced. This is necessary since
            RadDropDownList uses data virtualization, which might lead to unpredicted appearance results when
            items are being reused.
          ![dropdown-and-listcontrol-dropdownlist-customizing-items 001](images/dropdown-and-listcontrol-dropdownlist-customizing-items001.png)

#### __[C#] Customize selected item appearance__

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownListCustomizeItems.cs region=CustomizeItems}}
	
	        private void radDropDownList1_VisualListItemFormatting(object sender, VisualItemFormattingEventArgs args)
	        {
	            if (args.VisualItem.Selected)
	            {
	                args.VisualItem.NumberOfColors = 1;
	                args.VisualItem.BackColor = Color.Yellow;
	                args.VisualItem.BorderColor = Color.Blue;
	            }
	            else
	            {
	                args.VisualItem.ResetValue(LightVisualElement.NumberOfColorsProperty, Telerik.WinControls.ValueResetFlags.Local);
	                args.VisualItem.ResetValue(LightVisualElement.BackColorProperty, Telerik.WinControls.ValueResetFlags.Local);
	                args.VisualItem.ResetValue(LightVisualElement.BorderColorProperty, Telerik.WinControls.ValueResetFlags.Local);
	            }
	        }
	
	{{endregion}}



#### __[VB.NET] Customize selected item appearance__

{{source=..\SamplesVB\DropDownListControl\DropDownList\DropDownListCustomizeItems.vb region=CustomizeItems}}
	    Private Sub radDropDownList1_VisualListItemFormatting(sender As Object, args As VisualItemFormattingEventArgs)
	        If args.VisualItem.Selected Then
	            args.VisualItem.NumberOfColors = 1
	            args.VisualItem.BackColor = Color.Yellow
	            args.VisualItem.BorderColor = Color.Blue
	        Else
	            args.VisualItem.ResetValue(LightVisualElement.NumberOfColorsProperty, Telerik.WinControls.ValueResetFlags.Local)
	            args.VisualItem.ResetValue(LightVisualElement.BackColorProperty, Telerik.WinControls.ValueResetFlags.Local)
	            args.VisualItem.ResetValue(LightVisualElement.BorderColorProperty, Telerik.WinControls.ValueResetFlags.Local)
	        End If
	    End Sub
	{{endregion}}



## Customizing auto-complete dropdown appearance

In order to customize the auto complete popup, you should subscribe to the __VisualItemFormatting__
          event of the __AutoCompleteSuggestHelper__. The following code snippet demonstrates
          how to change the font of the auto complete drop down items:
        

#### __[C#] Subscribe to the VisualItemFormatting event of the auto complete popup__

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownListCustomizeItems.cs region=SubscribeToAutoCompleteSuggestVisualItemFormattingEvent}}
	
	            radDropDownList1.DropDownListElement.AutoCompleteSuggest.DropDownList.ListElement.VisualItemFormatting += new VisualListItemFormattingEventHandler(ListElement_VisualItemFormatting);
	
	{{endregion}}



#### __[VB.NET] Subscribe to the VisualItemFormatting event of the auto complete popup__





The following code snippet, will demonstrate how to change the Font of all items in the
          auto complete drop down.
        

#### __[C#] Customize auto complete items appearance__

{{source=..\SamplesCS\DropDownListControl\DropDownList\DropDownListCustomizeItems.cs region=CustomizeAutoCompleteDropDown}}
	
	        Font myFont = new Font("Segoe UI", 14, FontStyle.Bold);
	
	        private void ListElement_VisualItemFormatting(object sender, VisualItemFormattingEventArgs args)
	        {
	            args.VisualItem.Font = myFont;
	        }
	
	{{endregion}}



#### __[VB.NET] Customize auto complete items appearance__

{{source=..\SamplesVB\DropDownListControl\DropDownList\DropDownListCustomizeItems.vb region=CustomizeAutoCompleteDropDown}}
	
	    Private myFont As New Font("Segoe UI", 14, FontStyle.Bold)
	
	    Private Sub ListElement_VisualItemFormatting(sender As Object, args As VisualItemFormattingEventArgs)
	        args.VisualItem.Font = myFont
	    End Sub
	
	{{endregion}}



>Here we do not reset the style because we do want the Font for all items to be changed not only
            on certain one.
          ![dropdown-and-listcontrol-dropdownlist-customizing-items 002](images/dropdown-and-listcontrol-dropdownlist-customizing-items002.png)