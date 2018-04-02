---
UID: NF:wdtf.IWDTFActions2.Remove
title: IWDTFActions2::Remove method
author: windows-driver-content
description: Remove an action from the collection.
old-location: dtf\iwdtfactions2_remove.htm
old-project: dtf
ms.assetid: 28cebd7f-1f88-4c3d-8432-c44df4e287d7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IWDTFActions2, IWDTFActions2 interface [Windows Device Testing Framework], Remove method, IWDTFActions2::Remove, Remove method [Windows Device Testing Framework], Remove method [Windows Device Testing Framework], IWDTFActions2 interface, Remove,IWDTFActions2.Remove, dtf.iwdtfactions2_remove, wdtf/IWDTFActions2::Remove
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wdtf.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Wdtf.idl
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
-	wdtf.h
api_name:
-	IWDTFActions2.Remove
product: Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFActions2::Remove method
Remove an action from the collection.

## Syntax

```
HRESULT Remove(
  IWDTFAction2 *pAction
);
```

## Parameters

`pAction`

The action to remove from this collection.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

The lifetime of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406311">IWDTFAction2</a> interface 
instances are tied to their creator. If you remove an item from a collection, the item is
not destroyed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406331">IWDTFActions2</a>