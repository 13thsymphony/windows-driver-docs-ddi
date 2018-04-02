---
UID: NS:ntddk._MM_COPY_ADDRESS
title: "_MM_COPY_ADDRESS"
author: windows-driver-content
description: The MM_COPY_ADDRESS structure contains either a virtual memory address or a physical memory address.
old-location: kernel\mm_copy_address.htm
old-project: kernel
ms.assetid: 9C9A0D46-587C-43F3-808E-38E81CE3EE50
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PMMCOPY_ADDRESS, MM_COPY_ADDRESS, MM_COPY_ADDRESS structure [Kernel-Mode Driver Architecture], PMM_COPY_ADDRESS, PMM_COPY_ADDRESS structure pointer [Kernel-Mode Driver Architecture], _MM_COPY_ADDRESS, kernel.mm_copy_address, ntddk/MM_COPY_ADDRESS, ntddk/PMM_COPY_ADDRESS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddk.h
api_name:
-	MM_COPY_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: MM_COPY_ADDRESS, *PMMCOPY_ADDRESS
---

# _MM_COPY_ADDRESS structure
The <b>MM_COPY_ADDRESS</b> structure contains either a virtual memory address or a physical memory address.

## Syntax
```
typedef struct _MM_COPY_ADDRESS {
  union {
    PHYSICAL_ADDRESS PhysicalAddress;
    PVOID            VirtualAddress;
  };
} *PMMCOPY_ADDRESS, MM_COPY_ADDRESS;
```

## Members


## Remarks
This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/dn342884">MmCopyMemory</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8.1. Supported starting with Windows 8.1. |
| **Header** | ntddk.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn342884">MmCopyMemory</a>