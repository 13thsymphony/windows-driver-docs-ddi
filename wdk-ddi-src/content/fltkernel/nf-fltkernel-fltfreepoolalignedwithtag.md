---
UID: NF:fltkernel.FltFreePoolAlignedWithTag
title: FltFreePoolAlignedWithTag function
author: windows-driver-content
description: The FltFreePoolAlignedWithTag routine frees a cache-aligned buffer that was allocated by a previous call to FltAllocatePoolAlignedWithTag.
old-location: ifsk\fltfreepoolalignedwithtag.htm
old-project: ifsk
ms.assetid: 295a34e4-734e-41ba-bf2e-378333c14e2c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: FltApiRef_e_to_o_dc83e564-1331-48f0-ad7e-8cdeaa677952.xml, FltFreePoolAlignedWithTag, FltFreePoolAlignedWithTag routine [Installable File System Drivers], fltkernel/FltFreePoolAlignedWithTag, ifsk.fltfreepoolalignedwithtag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: 
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltFreePoolAlignedWithTag
product:
- Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltFreePoolAlignedWithTag function
The <b>FltFreePoolAlignedWithTag</b> routine frees a cache-aligned buffer that was allocated by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>.

## Syntax

```
VOID FLTAPI FltFreePoolAlignedWithTag(
  PFLT_INSTANCE Instance,
  PVOID         Buffer,
  ULONG         Tag
);
```

## Parameters

`Instance`

Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. Must be the same instance pointer as the one used in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>.

`Buffer`

Address of the block of pool memory to be freed.

`Tag`

Tag used to mark the pool block. Must be the same tag as the one used in the call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>.


## Return Value

None

## Remarks

The memory that the <i>Buffer</i> parameter points to must not be accessed after it is freed by <b>FltFreePoolAlignedWithTag</b>. 

The caller of <b>FltFreePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL if a <b>NonPaged</b><i>XxxPoolType</i> value was specified when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541762">FltAllocatePoolAlignedWithTag</a>