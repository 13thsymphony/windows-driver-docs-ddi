---
UID: NF:printerextension.IPrintSchemaCapabilities.GetFeatureByKeyName
title: IPrintSchemaCapabilities::GetFeatureByKeyName method
author: windows-driver-content
description: Gets a feature from the PrintCapabilities based on a given key name.
old-location: print\iprintschemacapabilities_getfeaturebykeyname.htm
old-project: print
ms.assetid: 053BFE59-FDC6-42F3-BE14-CE63D5637D62
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintSchemaCapabilities, IPrintSchemaCapabilities::GetFeatureByKeyName, GetFeatureByKeyName
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
req.alt-api: IPrintSchemaCapabilities.GetFeatureByKeyName
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
req.irql: 
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrintSchemaCapabilities::GetFeatureByKeyName method



## -description
Gets a feature from the PrintCapabilities based on a given key name.



## -syntax

````
HRESULT GetFeatureByKeyName(
  [in]          BSTR                bstrKeyName,
  [out, retval] IPrintSchemaFeature **ppFeature
);
````


## -parameters

### -param bstrKeyName [in]

The key name of the feature.


### -param ppFeature [out, retval]

The returned feature.


## -returns
This method returns an <b>HRESULT</b> value.


## -remarks
Only the following feature key names are recognized. The key names are equivalent to public Print Schema feature names as shown in the following table. The table also shows the features that have specialized option types (by default the option type is <a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>).

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object and query it via <b>IPrintSchemaCapabilities::GetFeatureByKeyName</b> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Windows 8

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
<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemanupoption.md">IPrintSchemaNUpOption</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemaoption.md">IPrintSchemaOption</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md">IPrintSchemaPageMediaSizeOption</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaCapabilities::GetFeatureByKeyName method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

