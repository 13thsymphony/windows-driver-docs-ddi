---
UID: NF:wdtf.IWDTFActions2.Add
title: IWDTFActions2::Add method
author: windows-driver-content
description: Add a single action to the collection.
old-location: dtf\iwdtfactions2_add.htm
old-project: dtf
ms.assetid: a6361d17-419f-4e34-b36f-5258dd34cc88
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: Add method [Windows Device Testing Framework], Add method [Windows Device Testing Framework], IWDTFActions2 interface, Add,IWDTFActions2.Add, IWDTFActions2, IWDTFActions2 interface [Windows Device Testing Framework], Add method, IWDTFActions2::Add, dtf.iwdtfactions2_add, wdtf/IWDTFActions2::Add
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
-	IWDTFActions2.Add
product:
- Windows
targetos: Windows
req.typenames: TTraceLevel
req.product: Windows 10 or later.
---


# IWDTFActions2::Add method
Add a single action to the collection.

## Syntax

```
HRESULT Add(
  IWDTFAction2 *pAction
);
```

## Parameters

`pAction`

The action to add to this collection.


## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdtf.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406331">IWDTFActions2</a>