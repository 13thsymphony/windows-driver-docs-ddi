---
UID: NN.printerextension.IPrintSchemaTicket~r1
title: IPrintSchemaTicket
author: windows-driver-content
description: Provides the primary method to access and validate a PrintTicket.
old-location: print\iprintschematicket_interface.htm
old-project: print
ms.assetid: 190B0B88-6018-4B43-8699-78427421D6FF
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
req.alt-api: IPrintSchemaTicket
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

# IPrintSchemaTicket interface



## -description
Provides the primary method to access and validate a PrintTicket.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>. <b>IPrintSchemaTicket</b> also has these types of members:

The <b>IPrintSchemaTicket</b> interface has these methods.

Gets an  asynchronous PrintTicket commit operation context.

Gets an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.

Gets a named feature from the PrintTicket, by name and full namespace URI.

Gets a feature from the PrintTicket based on the specified key name.

Notifies the print system that the XML DOM object has changed.

Gets an asynchronous PrintTicket validation operation context.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface has these properties.


<a href="print.iprintschematicket_jobcopiesalldocuments">JobCopiesAllDocuments</a>


Read-only

Gets the copy count.


<a href="print.iprintschematicket_put_jobcopiesalldocuments">JobCopiesAllDocuments</a>


Write-only

Sets the copy count.

 


## -members
The <b>IPrintSchemaTicket</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_commitasync">CommitAsync</a>
</td>
<td align="left" width="63%">
Gets an  asynchronous PrintTicket commit operation context.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_getcapabilities">GetCapabilities</a>
</td>
<td align="left" width="63%">
Gets an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_getfeature">GetFeature</a>
</td>
<td align="left" width="63%">
Gets a named feature from the PrintTicket, by name and full namespace URI.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_getfeaturebykeyname">GetFeatureByKeyName</a>
</td>
<td align="left" width="63%">
Gets a feature from the PrintTicket based on the specified key name.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_notifyxmlchanged">NotifyXmlChanged</a>
</td>
<td align="left" width="63%">
Notifies the print system that the XML DOM object has changed.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschematicket_validateasync">ValidateAsync</a>
</td>
<td align="left" width="63%">
Gets an asynchronous PrintTicket validation operation context.

</td>
</tr>
</table>Gets an  asynchronous PrintTicket commit operation context.

Gets an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <b>IPrintSchemaTicket</b> object.

Gets a named feature from the PrintTicket, by name and full namespace URI.

Gets a feature from the PrintTicket based on the specified key name.

Notifies the print system that the XML DOM object has changed.

Gets an asynchronous PrintTicket validation operation context.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaTicket</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschematicket_jobcopiesalldocuments">JobCopiesAllDocuments</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the copy count.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschematicket_put_jobcopiesalldocuments">JobCopiesAllDocuments</a>


</td>
<td align="left" width="10%">
Write-only

</td>
<td align="left" width="63%">
Sets the copy count.

</td>
</tr>
</table>
<a href="print.iprintschematicket_jobcopiesalldocuments">JobCopiesAllDocuments</a>


Read-only

Gets the copy count.


<a href="print.iprintschematicket_put_jobcopiesalldocuments">JobCopiesAllDocuments</a>


Write-only

Sets the copy count.

 


## -remarks
To obtain an IXMLDOMDocument2 object for the PrintTicket object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="print.iprintschemaelement_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintTicket object to access the underlying  IXMLDOMDocument2 object.


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
<a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>
</dt>
<dt>
<a href="print.iprintschemaasyncoperationevent_completed">IPrintSchemaAsyncOperationEvent::Completed</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>
</dt>
<dt>
<a href="print.iprintschemaelement_xmlnode">IPrintSchemaElement::XmlNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket interface%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

