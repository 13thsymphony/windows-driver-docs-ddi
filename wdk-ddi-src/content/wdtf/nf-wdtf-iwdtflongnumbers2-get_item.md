---
UID: NF:wdtf.IWDTFLongNumbers2.get_Item
title: IWDTFLongNumbers2::get_Item method
author: windows-driver-content
description: Gets an individual long number in the collection.
old-location: dtf\iwdtflongnumbers2_item.htm
old-project: dtf
ms.assetid: 52c2a15c-13ec-43a1-ad8e-fc55ef681a60
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFLongNumbers2, IWDTFLongNumbers2 interface [Windows Device Testing Framework], Item property, IWDTFLongNumbers2.Item, IWDTFLongNumbers2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFLongNumbers2 interface, Microsoft.WDTF.IWDTFLongNumbers2.Item, Microsoft::WDTF::IWDTFLongNumbers2::Item, dtf.iwdtflongnumbers2_item, get_Item,IWDTFLongNumbers2.get_Item, wdtf/IWDTFLongNumbers2::Item, wdtf/IWDTFLongNumbers2::get_Item
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
-	IWDTFLongNumbers2.Item
-	IWDTFLongNumbers2.get_Item
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFLongNumbers2::get_Item method
Gets an individual long number in the collection.

This property is read-only.

## Syntax

```
HRESULT get_Item(
  LONG     Index,
  LONGLONG *pNumber
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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451027">IWDTFLongNumbers2</a>