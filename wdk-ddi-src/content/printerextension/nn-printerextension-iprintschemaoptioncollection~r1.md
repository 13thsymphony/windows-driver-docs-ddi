---
UID: NN.printerextension.IPrintSchemaOptionCollection~r1
title: IPrintSchemaOptionCollection
author: windows-driver-content
description: Exposes a collection of IPrintSchemaOption objects.
old-location: print\iprintschemaoptioncollection.htm
old-project: print
ms.assetid: ED0FD042-EB42-4F4B-AF9C-B8F56909ED66
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
req.alt-api: IPrintSchemaOptionCollection
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

# IPrintSchemaOptionCollection interface



## -description
Exposes a collection of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IDispatch</b></a> interface. <b>IPrintSchemaOptionCollection</b> also has these types of members:

The <b>IPrintSchemaOptionCollection</b> interface has these methods.

Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface has these properties.


<a href="print.iprintschemaoptioncollection_count">Count</a>


Read-only

Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects in the collection.


<a href="print.iprintschemaoptioncollection_newenum">NewEnum</a>


Read-only

Gets a pointer to the enumerants of <b>IPrintSchemaOptionCollection</b> objects.

 


## -members
The <b>IPrintSchemaOptionCollection</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemaoptioncollection_getat">GetAt</a>
</td>
<td align="left" width="63%">
Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.

</td>
</tr>
</table>Gets a pointer to an <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> object.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaOptionCollection</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemaoptioncollection_count">Count</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects in the collection.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemaoptioncollection_newenum">NewEnum</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets a pointer to the enumerants of <b>IPrintSchemaOptionCollection</b> objects.

</td>
</tr>
</table>
<a href="print.iprintschemaoptioncollection_count">Count</a>


Read-only

Gets a count of the number of <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a> objects in the collection.


<a href="print.iprintschemaoptioncollection_newenum">NewEnum</a>


Read-only

Gets a pointer to the enumerants of <b>IPrintSchemaOptionCollection</b> objects.

 


## -remarks


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
<a href="automat.idispatch">IDispatch</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaOptionCollection interface%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

