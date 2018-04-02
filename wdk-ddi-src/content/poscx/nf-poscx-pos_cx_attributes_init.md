---
UID: NF:poscx.POS_CX_ATTRIBUTES_INIT
title: POS_CX_ATTRIBUTES_INIT function
author: windows-driver-content
description: POS_CX_ATTRIBUTES_INIT initializes a POS_CX_ATTRIBUTE structure.
old-location: pos\pos_cx_attributes_init.htm
old-project: pos
ms.assetid: A1287386-E831-474A-858C-89787741FD57
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: POS_CX_ATTRIBUTES_INIT, POS_CX_ATTRIBUTES_INIT function, pos.pos_cx_attributes_init, poscx/POS_CX_ATTRIBUTES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: poscx.h
req.include-header: Poscx.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	poscx.h
api_name:
-	POS_CX_ATTRIBUTES_INIT
product:
- Windows
targetos: Windows
req.typenames: POS_CX_EVENT_PRIORITY
req.product: Windows 10 or later.
---


# POS_CX_ATTRIBUTES_INIT function
POS_CX_ATTRIBUTES_INIT initializes a <a href="https://msdn.microsoft.com/A91B8EAA-2FCB-4468-8CF3-A3C4D9D7E355">POS_CX_ATTRIBUTE</a> structure.

## Syntax

```
void POS_CX_ATTRIBUTES_INIT(
  POS_CX_ATTRIBUTES *PosCxAttrPtr
);
```

## Parameters

`PosCxAttrPtr`

A pointer to the caller-allocated <a href="https://msdn.microsoft.com/A91B8EAA-2FCB-4468-8CF3-A3C4D9D7E355">POS_CX_ATTRIBUTE</a> structure to initialize.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | poscx.h (include Poscx.h) |

## See Also

<a href="https://msdn.microsoft.com/A91B8EAA-2FCB-4468-8CF3-A3C4D9D7E355">POS_CX_ATTRIBUTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt593125">PosCxInit</a>