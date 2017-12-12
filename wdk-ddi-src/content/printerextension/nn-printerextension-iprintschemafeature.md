---
UID: NN.printerextension.IPrintSchemaFeature
title: IPrintSchemaFeature
author: windows-driver-content
description: Exposes a Print Schema Feature element.
old-location: print\iprintschemafeature_interface.htm
old-project: print
ms.assetid: AAC2A60B-9E70-4809-969A-68783A91B093
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: tagPrintSchemaSelectionType, PrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaFeature
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IPrintSchemaFeature interface



## -description
Exposes a Print Schema Feature element.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaFeature</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprintschemadisplayableelement.md">IPrintSchemaDisplayableElement</a>. <b>IPrintSchemaFeature</b> also has these types of members:

The <b>IPrintSchemaFeature</b> interface has these methods.

Gets the option with the given name.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaFeature</b> interface has these properties.


<a href="print.iprintschemafeature_displayui">DisplayUI</a>


Read-only

Gets the setting that indicates whether or not to show the print UI.


<a href="print.iprintschemafeature_selectedoption">SelectedOption</a>


Read-only

Gets an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> representing the selected option.


<a href="print.iprintschemafeature_put_selectedoption">SelectedOption</a>


Write-only

Changes the selected option of the Print Schema Feature element to the specified <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> element.


<a href="print.iprintschemafeature_selectiontype">SelectionType</a>


Read-only

Gets the selection type of the Feature.

 


## -members
The <b>IPrintSchemaFeature</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemafeature_getoption">GetOption</a>
</td>
<td align="left" width="63%">
Gets the option with the given name.

</td>
</tr>
</table>Gets the option with the given name.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaFeature</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemafeature_displayui">DisplayUI</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the setting that indicates whether or not to show the print UI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemafeature_selectedoption">SelectedOption</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> representing the selected option.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemafeature_put_selectedoption">SelectedOption</a>


</td>
<td align="left" width="10%">
Write-only

</td>
<td align="left" width="63%">
Changes the selected option of the Print Schema Feature element to the specified <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> element.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemafeature_selectiontype">SelectionType</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the selection type of the Feature.

</td>
</tr>
</table>
<a href="print.iprintschemafeature_displayui">DisplayUI</a>


Read-only

Gets the setting that indicates whether or not to show the print UI.


<a href="print.iprintschemafeature_selectedoption">SelectedOption</a>


Read-only

Gets an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> representing the selected option.


<a href="print.iprintschemafeature_put_selectedoption">SelectedOption</a>


Write-only

Changes the selected option of the Print Schema Feature element to the specified <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> element.


<a href="print.iprintschemafeature_selectiontype">SelectionType</a>


Read-only

Gets the selection type of the Feature.

 


## -remarks
You must ensure that each Feature or Option in a PrintTicket or PrintCapabilities XML document has a <i>name</i> attribute specified. This attribute is used to build the <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> and <b>IPrintSchemaFeature</b> objects. If the <i>name</i> attribute is omitted, the feature or option will not be displayed in the object model, or the Microsoft-provided print preferences experience.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemadisplayableelement.md">IPrintSchemaDisplayableElement</a>
</dt>
<dt>
<a href="print.iprintschemacapabilities_getfeature">IPrintSchemaCapabilities::GetFeature</a>
</dt>
<dt>
<a href="print.iprintschematicket_getfeature">IPrintSchemaTicket::GetFeature</a>
</dt>
<dt>
<a href="print.iprintschematicket_getfeaturebykeyname">IPrintSchemaTicket::GetFeatureByKeyName</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaFeature interface%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

