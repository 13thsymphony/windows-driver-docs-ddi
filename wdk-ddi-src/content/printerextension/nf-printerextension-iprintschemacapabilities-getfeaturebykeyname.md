---
UID: NF:printerextension.IPrintSchemaCapabilities.GetFeatureByKeyName
title: IPrintSchemaCapabilities::GetFeatureByKeyName method
author: windows-driver-content
description: Gets a feature from the PrintCapabilities based on a given key name.
old-location: print\iprintschemacapabilities_getfeaturebykeyname.htm
old-project: print
ms.assetid: 053BFE59-FDC6-42F3-BE14-CE63D5637D62
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintSchemaCapabilities interface [Print Devices], GetFeatureByKeyName method, GetFeatureByKeyName method [Print Devices], IPrintSchemaCapabilities interface, IPrintSchemaCapabilities::GetFeatureByKeyName, GetFeatureByKeyName, GetFeatureByKeyName method [Print Devices], printerextension/IPrintSchemaCapabilities::GetFeatureByKeyName, print.iprintschemacapabilities_getfeaturebykeyname, IPrintSchemaCapabilities
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaCapabilities.GetFeatureByKeyName
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetFeatureByKeyName method
Gets a feature from the PrintCapabilities based on a given key name.

## Syntax

````
HRESULT GetFeatureByKeyName(
  [in]          BSTR                bstrKeyName,
  [out, retval] IPrintSchemaFeature **ppFeature
);
````

## Parameters

`bstrKeyName`

The key name of the feature.

`ppFeature`

The returned feature.


## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

Only the following feature key names are recognized. The key names are equivalent to public Print Schema feature names as shown in the following table. The table also shows the features that have specialized option types (by default the option type is <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>).

<table>
<tr>
<th>Name</th>
<th>Print schema feature public name</th>
<th>Specialized option type</th>
</tr>
<tr>
<td>DocumentBinding</td>
<td>DocumentBinding or JobBindAllDocuments</td>
<td></td>
</tr>
<tr>
<td>DocumentCollate</td>
<td>DocumentCollate</td>
<td></td>
</tr>
<tr>
<td>DocumentDuplex</td>
<td>JobDuplexAllDocumentsContiguously</td>
<td></td>
</tr>
<tr>
<td>DocumentHolePunch</td>
<td>DocumentHolePunch or JobHolePunch</td>
<td></td>
</tr>
<tr>
<td>DocumentInputBin</td>
<td>JobInputBin, DocumentInputBin or PageInputBin</td>
<td></td>
</tr>
<tr>
<td>DocumentNUp</td>
<td>JobNUpAllDocumentsContiguously</td>
<td>
<a href="..\printerextension\nn-printerextension-iprintschemanupoption.md">IPrintSchemaNUpOption</a>
</td>
</tr>
<tr>
<td>DocumentStaple</td>
<td>JobStapleAllDocuments or DocumentStaple</td>
<td></td>
</tr>
<tr>
<td>PageMediaSize</td>
<td>PageMediaSize</td>
<td>
<a href="..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md">IPrintSchemaPageMediaSizeOption</a>
</td>
</tr>
<tr>
<td>PageMediaType</td>
<td>PageMediaType</td>
<td></td>
</tr>
<tr>
<td>PageOrientation</td>
<td>PageOrientation</td>
<td></td>
</tr>
<tr>
<td>PageOutputColor</td>
<td>PageOutputColor</td>
<td></td>
</tr>
<tr>
<td>PageOutputQuality</td>
<td>PageOutputQuality</td>
<td></td>
</tr>
</table>
 

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object and query it via <b>IPrintSchemaCapabilities::GetFeatureByKeyName</b> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemanupoption.md">IPrintSchemaNUpOption</a>



<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>



<a href="..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md">IPrintSchemaPageMediaSizeOption</a>



<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::GetFeatureByKeyName method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>