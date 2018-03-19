---
UID: NC:wdm.MM_MDL_ROUTINE
title: MM_MDL_ROUTINE
author: windows-driver-content
description: A driver-supplied callback routine that is invoked after a memory descriptor list (MDL) is mapped by calling the MmMapMdl function.
old-location: kernel\mm_mdl_routine.htm
old-project: kernel
ms.assetid: D8D946C9-8642-4D31-B983-DAF88B46B97B
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PMM_MDL_ROUTINE, *PMM_MDL_ROUTINE callback function [Kernel-Mode Driver Architecture], MM_MDL_ROUTINE, MmMdlRoutine, MmMdlRoutine callback function [Kernel-Mode Driver Architecture], kernel.mm_mdl_routine, wdm/MmMdlRoutine"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	*PMM_MDL_ROUTINE
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# MM_MDL_ROUTINE callback function
A driver-supplied callback routine that is invoked after a memory descriptor
    list (MDL)  is mapped by calling the <a href="..\wdm\nf-wdm-mmmapmdl.md">MmMapMdl</a> function.

## Syntax

```
MM_MDL_ROUTINE MmMdlRoutine;

void MmMdlRoutine(
  PVOID DriverContext,
  PVOID MappedVa
)
{...}
```

## Parameters

`DriverContext`

A pointer to a driver-defined context. The driver's callback function can store any status information  in the driver context and then examine the value, when the callback is invoked.

`MappedVa`

A pointer to a buffer that contains the system virtual address of the
        mapping.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | wdm.h |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-mmmapmdl.md">MmMapMdl</a>