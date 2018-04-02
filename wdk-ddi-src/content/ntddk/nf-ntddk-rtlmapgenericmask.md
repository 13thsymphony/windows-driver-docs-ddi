---
UID: NF:ntddk.RtlMapGenericMask
title: RtlMapGenericMask function
author: windows-driver-content
description: The RtlMapGenericMask routine determines the nongeneric access rights specified by an ACCESS_MASK.
old-location: kernel\rtlmapgenericmask.htm
old-project: kernel
ms.assetid: dd3a5f87-21a9-4186-bb74-a49e6751622e
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlMapGenericMask, RtlMapGenericMask routine [Kernel-Mode Driver Architecture], k109_f0e498a8-0b75-4fb8-a9c6-3f1ce3eb71f3.xml, kernel.rtlmapgenericmask, ntddk/RtlMapGenericMask
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlMapGenericMask
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlMapGenericMask function
The <b>RtlMapGenericMask</b> routine determines the nongeneric access rights specified by an ACCESS_MASK.

## Syntax

```
NTSYSAPI VOID RtlMapGenericMask(
  PACCESS_MASK     AccessMask,
  PGENERIC_MAPPING GenericMapping
);
```

## Parameters

`AccessMask`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> variable. The routine updates this to contain only those access rights that are not also granted by any GENERIC_<i>XXX</i> access rights originally specified the variable. The routine also clears any GENERIC_<i>XXX</i> bits that are set.

`GenericMapping`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a> structure that describes the specific access rights that correspond to each generic access right.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>