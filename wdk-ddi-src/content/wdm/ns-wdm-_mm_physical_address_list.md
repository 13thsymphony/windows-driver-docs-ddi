---
UID: NS:wdm._MM_PHYSICAL_ADDRESS_LIST
title: "_MM_PHYSICAL_ADDRESS_LIST"
author: windows-driver-content
description: The MM_PHYSICAL_ADDRESS_LIST structure specifies a range of physical addresses.
old-location: kernel\mm_physical_address_list.htm
old-project: kernel
ms.assetid: D653607A-7C37-408D-AD19-B4A8988CDACE
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PMM_PHYSICAL_ADDRESS_LIST, MM_PHYSICAL_ADDRESS_LIST, MM_PHYSICAL_ADDRESS_LIST structure [Kernel-Mode Driver Architecture], PMM_PHYSICAL_ADDRESS_LIST, PMM_PHYSICAL_ADDRESS_LIST structure pointer [Kernel-Mode Driver Architecture], _MM_PHYSICAL_ADDRESS_LIST, kernel.mm_physical_address_list, wdm/MM_PHYSICAL_ADDRESS_LIST, wdm/PMM_PHYSICAL_ADDRESS_LIST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MM_PHYSICAL_ADDRESS_LIST
product: Windows
targetos: Windows
req.typenames: MM_PHYSICAL_ADDRESS_LIST, *PMM_PHYSICAL_ADDRESS_LIST
req.product: Windows 10 or later.
---

# _MM_PHYSICAL_ADDRESS_LIST structure
The <b>MM_PHYSICAL_ADDRESS_LIST</b> structure specifies a range of physical addresses.

## Syntax
```
typedef struct _MM_PHYSICAL_ADDRESS_LIST {
  PHYSICAL_ADDRESS PhysicalAddress;
  SIZE_T           NumberOfBytes;
} MM_PHYSICAL_ADDRESS_LIST, *PMM_PHYSICAL_ADDRESS_LIST;
```

## Members


`PhysicalAddress`

The starting physical address of the range. This address must be aligned to a page boundary in physical memory.

`NumberOfBytes`

The number of bytes in the range. This member must be nonzero and an integer multiple of the memory page size.

## Remarks
The first parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/jj206443">MmAllocateMdlForIoSpace</a> routine is a pointer to an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj206443">MmAllocateMdlForIoSpace</a>