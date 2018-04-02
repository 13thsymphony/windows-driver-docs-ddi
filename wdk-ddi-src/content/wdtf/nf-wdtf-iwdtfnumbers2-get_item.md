---
UID: NF:wdtf.IWDTFNumbers2.get_Item
title: IWDTFNumbers2::get_Item method
author: windows-driver-content
description: Gets an individual number in the collection.
old-location: dtf\iwdtfnumbers2_item.htm
old-project: dtf
ms.assetid: 619cff76-96a6-4aa6-bfdf-67c40e21b4a0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFNumbers2, IWDTFNumbers2 interface [Windows Device Testing Framework], Item property, IWDTFNumbers2.Item, IWDTFNumbers2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFNumbers2 interface, Microsoft.WDTF.IWDTFNumbers2.Item, Microsoft::WDTF::IWDTFNumbers2::Item, dtf.iwdtfnumbers2_item, get_Item,IWDTFNumbers2.get_Item, wdtf/IWDTFNumbers2::Item, wdtf/IWDTFNumbers2::get_Item
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
-	IWDTFNumbers2.Item
-	IWDTFNumbers2.get_Item
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFNumbers2::get_Item method
Gets an individual number in the collection.

This property is read-only.

## Syntax

```
HRESULT get_Item(
  LONG Index,
  LONG *pNumber
);
```

## Parameters

`Index`



`pNumber`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451048">IWDTFNumbers2</a>