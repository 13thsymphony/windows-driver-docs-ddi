---
UID: NN.printerextension.IPrintSchemaCapabilities~r1
title: IPrintSchemaCapabilities
author: windows-driver-content
description: Provides the primary method to access PrintCapabilities.
old-location: print\iprintschemacapabilities_interface.htm
old-project: print
ms.assetid: A148C1B4-99A3-4AF3-B2D6-73684978425F
ms.author: windowsdriverdev
ms.date: 11/24/2017
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
req.alt-api: IPrintSchemaCapabilities
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

# IPrintSchemaCapabilities interface



## -description
Provides the primary method to access PrintCapabilities.


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>. <b>IPrintSchemaCapabilities</b> also has these types of members:

The <b>IPrintSchemaCapabilities</b> interface has these methods.

Gets a named feature from the PrintCapabilities, by name and full namespace URI.

Gets a feature from the PrintCapabilities based on a given key name.

Gets all the options of a feature.

Gets the selected option for a feature in <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface has these properties.


<a href="print.iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue">JobCopiesAllDocumentsMaxValue</a>


Read-only

Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.


<a href="print.iprintschemacapabilities_jobcopiesalldocumentsminvalue">JobCopiesAllDocumentsMinValue</a>


Read-only

Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.


<a href="print.iprintschemacapabilities_pageimageablesize">PageImageableSize</a>


Read-only

Gets the imageable area information of the printer.

 

## -members
The <b>IPrintSchemaCapabilities</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemacapabilities_getfeature">GetFeature</a>
</td>
<td align="left" width="63%">
Gets a named feature from the PrintCapabilities, by name and full namespace URI.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemacapabilities_getfeaturebykeyname">GetFeatureByKeyName</a>
</td>
<td align="left" width="63%">
Gets a feature from the PrintCapabilities based on a given key name.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemacapabilities_getoptions">GetOptions</a>
</td>
<td align="left" width="63%">
Gets all the options of a feature.
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprintschemacapabilities_getselectedoptioninprintticket">GetSelectedOptionInPrintTicket</a>
</td>
<td align="left" width="63%">
Gets the selected option for a feature in <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>.
</td>
</tr>
</table>Gets a named feature from the PrintCapabilities, by name and full namespace URI.

Gets a feature from the PrintCapabilities based on a given key name.

Gets all the options of a feature.

Gets the selected option for a feature in <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrintSchemaCapabilities</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue">JobCopiesAllDocumentsMaxValue</a>

</td>
<td align="left" width="10%">
Read-only
</td>
<td align="left" width="63%">
Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.
</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemacapabilities_jobcopiesalldocumentsminvalue">JobCopiesAllDocumentsMinValue</a>

</td>
<td align="left" width="10%">
Read-only
</td>
<td align="left" width="63%">
Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.
</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="print.iprintschemacapabilities_pageimageablesize">PageImageableSize</a>

</td>
<td align="left" width="10%">
Read-only
</td>
<td align="left" width="63%">
Gets the imageable area information of the printer.
</td>
</tr>
</table>
<a href="print.iprintschemacapabilities_get_jobcopiesalldocumentsmaxvalue">JobCopiesAllDocumentsMaxValue</a>


Read-only

Gets the <b>JobCopiesAllDocuments</b> parameter maximum value.


<a href="print.iprintschemacapabilities_jobcopiesalldocumentsminvalue">JobCopiesAllDocumentsMinValue</a>


Read-only

Gets the <b>JobCopiesAllDocuments</b> parameter minimum value.


<a href="print.iprintschemacapabilities_pageimageablesize">PageImageableSize</a>


Read-only

Gets the imageable area information of the printer.

 

## -remarks
To obtain an IXMLDOMDocument2 object for the PrintCapabilities object, you must first dereference the <i>ppXmlNode</i> parameter of the <a href="print.iprintschemaelement_xmlnode">XmlNode</a> property (using *ppXmlNode ). This retrieves a pointer to an interface of type <b>IUnknown</b>. Use this pointer to  call the <b>QueryInterface</b> method of the PrintCapabilities object to access the underlying  IXMLDOMDocument2 object.

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
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/hardware/br259124">Developing v4 print drivers</a></dt>
<dt>
<a href="print.iprintschemaelement_xmlnode">IPrintSchemaElement::XmlNode</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>
</dt>
<dt>
<a href="print.iprintschematicket_getcapabilities">IPrintSchemaTicket_GetCapabilities</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5C587AF2-C51E-4728-A214-7FC1F8A6E445">V4 Printer Driver Localization</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities interface%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
