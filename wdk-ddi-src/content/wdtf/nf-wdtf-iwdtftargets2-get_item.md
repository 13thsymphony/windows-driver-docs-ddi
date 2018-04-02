---
UID: NF:wdtf.IWDTFTargets2.get_Item
title: IWDTFTargets2::get_Item method
author: windows-driver-content
description: Gets an individual item in the collection.
old-location: dtf\iwdtftargets2_item.htm
old-project: dtf
ms.assetid: 886c71d2-2ee7-4ee9-aa40-68add721b1a9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], Item property, IWDTFTargets2.Item, IWDTFTargets2::get_Item, Item property [Windows Device Testing Framework], Item property [Windows Device Testing Framework], IWDTFTargets2 interface, Microsoft.WDTF.IWDTFTargets2.Item, Microsoft::WDTF::IWDTFTargets2::Item, dtf.iwdtftargets2_item, get_Item,IWDTFTargets2.get_Item, wdtf/IWDTFTargets2::Item, wdtf/IWDTFTargets2::get_Item
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
-	IWDTFTargets2.Item
-	IWDTFTargets2.get_Item
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTargets2::get_Item method
Gets an individual item in the collection.

This property is read-only.

## Syntax

```
HRESULT get_Item(
  LONG         Index,
  IWDTFTarget2 **ppTarget
);
```

## Parameters

`Index`



`ppTarget`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Windows |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a>