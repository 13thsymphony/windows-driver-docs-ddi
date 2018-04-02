---
UID: NF:wdtf.IWDTFStrings2.get_Item
title: IWDTFStrings2::get_Item method
author: windows-driver-content
description: Gets an individual string in the collection.
old-location: dtf\iwdtfstrings2_item.htm
old-project: dtf
ms.assetid: 01fe6cb0-5867-440f-b4ad-79bc946260b1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFStrings2, IWDTFStrings2 interface [Windows Device Testing Framework], Item property, IWDTFStrings2.Item, IWDTFStrings2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFStrings2 interface, Microsoft.WDTF.IWDTFStrings2.Item, Microsoft::WDTF::IWDTFStrings2::Item, dtf.iwdtfstrings2_item, get_Item,IWDTFStrings2.get_Item, wdtf/IWDTFStrings2::Item, wdtf/IWDTFStrings2::get_Item
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows XP Professional
req.target-min-winversvr: Windows Server 2008
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: WDTF.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTF.Interop.metadata_dll
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
-	WDTF.Interop.metadata_dll.dll
api_name:
-	IWDTFStrings2.Item
-	IWDTFStrings2.get_Item
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFStrings2::get_Item method
Gets an individual string in the collection.

This property is read-only.

## Syntax

```
HRESULT get_Item(
  LONG Index,
  BSTR *pString
);
```

## Parameters

`Index`



`pString`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439274">IWDTFStrings2</a>