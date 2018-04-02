---
UID: NF:wdtf.IWDTFTargets2.Remove
title: IWDTFTargets2::Remove method
author: windows-driver-content
description: Removes an item from the collection.
old-location: dtf\iwdtftargets2_remove.htm
old-project: dtf
ms.assetid: 5db8c912-a446-4ae7-a775-f56ffa979283
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFTargets2, IWDTFTargets2 interface [Windows Device Testing Framework], Remove method, IWDTFTargets2::Remove, Microsoft.WDTF.IWDTFTargets2.Remove, Microsoft::WDTF::IWDTFTargets2::Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework], IWDTFTargets2 interface, Remove,IWDTFTargets2.Remove, dtf.iwdtftargets2_remove, wdtf/IWDTFTargets2::Remove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
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
-	IWDTFTargets2.Remove
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFTargets2::Remove method
Removes an item from the collection.

## Syntax

```
HRESULT Remove(
  IWDTFTarget2 *pTarget
);
```

## Parameters

`pTarget`

The item to remove from this collection.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh439367">IWDTFTarget2</a> interface 
instances are tied to their creator. If you remove an item from a collection, the item is
not destroyed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows XP Professional Windows Server 2008 |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439458">IWDTFTargets2</a>