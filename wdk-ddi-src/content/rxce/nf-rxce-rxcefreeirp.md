---
UID: NF:rxce.RxCeFreeIrp
title: RxCeFreeIrp function
author: windows-driver-content
description: RxCeFreeIrp frees an IRP.
old-location: ifsk\rxcefreeirp.htm
old-project: ifsk
ms.assetid: 71e3283c-2dbc-4579-a374-e51e123b852f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxCeFreeIrp, RxCeFreeIrp function [Installable File System Drivers], ifsk.rxcefreeirp, rxce/RxCeFreeIrp, rxref_93b8da8d-d9fe-41e3-8423-5b3d8102f7a7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxce.h
req.include-header: Rxce.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxce.h
api_name:
-	RxCeFreeIrp
product:
- Windows
targetos: Windows
req.typenames: RILWRITEPHONEBOOKENTRYPARAMS, *LPRILWRITEPHONEBOOKENTRYPARAMS
req.product: Windows 10 or later.
---


# RxCeFreeIrp function
<b>RxCeFreeIrp</b> frees an IRP.

## Syntax

```
void RxCeFreeIrp(
  PIRP pIrp
);
```

## Parameters

`pIrp`

A pointer to the IRP to be freed.


## Return Value

None

## Remarks

An IRP allocated with an associated memory descriptor list allocated with <b>RxCeAllocateIrpWithMDL</b> should be freed when the IRP is completed using <b>RxCeFreeIrp</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxce.h (include Rxce.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554414">MDL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553405">RxCeAllocateIrpWithMDL</a>