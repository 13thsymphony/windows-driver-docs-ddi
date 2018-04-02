---
UID: NF:printerextension.IPrintSchemaFeature.GetOption
title: IPrintSchemaFeature::GetOption method
author: windows-driver-content
description: Gets the option with the given name.
old-location: print\iprintschemafeature_getoption.htm
old-project: print
ms.assetid: C9C4E085-1F2A-4610-AF2A-8F87E5CE7BCA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetOption method [Print Devices], GetOption method [Print Devices], IPrintSchemaFeature interface, GetOption,IPrintSchemaFeature.GetOption, IPrintSchemaFeature, IPrintSchemaFeature interface [Print Devices], GetOption method, IPrintSchemaFeature::GetOption, print.iprintschemafeature_getoption, printerextension/IPrintSchemaFeature::GetOption
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaFeature.GetOption
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaFeature::GetOption method
Gets the option with the given name.

## Syntax

```
HRESULT GetOption(
  BSTR               bstrName,
  BSTR               bstrNamespaceUri,
  IPrintSchemaOption **ppOption
);
```

## Parameters

`bstrName`

The name of the option.

`bstrNamespaceUri`

The namespace URI of the option.

`ppOption`

The returned option.


## Return Value

This method returns an <b>HRESULT</b> value, if the call was successful. Otherwise it returns the appropriate error code.

## Remarks

When the requested feature, option or property is not found, this method returns S_FALSE and sets a NULL pointer on the output object of the feature, option or property.

So if the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a> object does not contain the specified feature, option or property, the app must obtain an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a> object and query it via <a href="https://msdn.microsoft.com/053BFE59-FDC6-42F3-BE14-CE63D5637D62">IPrintSchemaCapabilities::GetFeatureByKeyName</a> or via <a href="https://msdn.microsoft.com/AC6434F5-0892-4426-98BB-BC02AD17917B">IPrintSchemaCapabilities::GetFeature</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451256">IPrintSchemaCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451284">IPrintSchemaFeature</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451335">IPrintSchemaOption</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>