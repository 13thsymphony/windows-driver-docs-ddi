---
UID: NS:wdfmemory._WDF_MEMORY_DESCRIPTOR
title: "_WDF_MEMORY_DESCRIPTOR"
author: windows-driver-content
description: The WDF_MEMORY_DESCRIPTOR structure describes a memory buffer.
old-location: wdf\wdf_memory_descriptor.htm
old-project: wdf
ms.assetid: 0683cb81-4ae7-4296-b46a-ad2e8b25a781
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_MEMORY_DESCRIPTOR, DFMemoryObjectRef_2c2271fb-6f3f-466d-b1dd-d254bc7ec96e.xml, PWDF_MEMORY_DESCRIPTOR, PWDF_MEMORY_DESCRIPTOR structure pointer, WDF_MEMORY_DESCRIPTOR, WDF_MEMORY_DESCRIPTOR structure, _WDF_MEMORY_DESCRIPTOR, kmdf.wdf_memory_descriptor, wdf.wdf_memory_descriptor, wdfmemory/PWDF_MEMORY_DESCRIPTOR, wdfmemory/WDF_MEMORY_DESCRIPTOR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdfmemory.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfmemory.h
api_name:
-	WDF_MEMORY_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: WDF_MEMORY_DESCRIPTOR, *PWDF_MEMORY_DESCRIPTOR
req.product: Windows 10 or later.
---

# _WDF_MEMORY_DESCRIPTOR structure
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_MEMORY_DESCRIPTOR</b> structure describes a memory buffer.

## Syntax
````
typedef struct _WDF_MEMORY_DESCRIPTOR {
  WDF_MEMORY_DESCRIPTOR_TYPE Type;
  union {
    struct {
      PVOID Buffer;
      ULONG Length;
    } BufferType;
    struct {
      PMDL  Mdl;
      ULONG BufferLength;
    } MdlType;
    struct {
      WDFMEMORY         Memory;
      PWDFMEMORY_OFFSET Offsets;
    } HandleType;
  } u;
} WDF_MEMORY_DESCRIPTOR, *PWDF_MEMORY_DESCRIPTOR;
````

## Members


`Type`

A <a href="..\wdfmemory\ne-wdfmemory-_wdf_memory_descriptor_type.md">WDF_MEMORY_DESCRIPTOR_TYPE</a>-typed value that identifies the type of buffer description that this <b>WDF_MEMORY_DESCRIPTOR</b> structure contains.

`u`

A union of three structures, one of which describes a buffer.

## Remarks
The <b>WDF_MEMORY_DESCRIPTOR</b> structure is used as input to several of the framework's <a href="https://msdn.microsoft.com/29680C5C-C690-4560-B340-3565D219DFE8">I/O target object methods</a> and <a href="https://msdn.microsoft.com/CDD13B29-62C8-4CF7-9027-E55A5B37AA2E">USB device object methods</a>.

To initialize a <b>WDF_MEMORY_DESCRIPTOR</b> structure, your driver should call <a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_buffer.md">WDF_MEMORY_DESCRIPTOR_INIT_BUFFER</a>, or <a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_mdl.md">WDF_MEMORY_DESCRIPTOR_INIT_MDL</a>, or <a href="..\wdfmemory\nf-wdfmemory-wdf_memory_descriptor_init_handle.md">WDF_MEMORY_DESCRIPTOR_INIT_HANDLE</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfmemory.h (include Wdf.h) |

## See Also

<a href="..\wdfmemory\ns-wdfmemory-_wdfmemory_offset.md">WDFMEMORY_OFFSET</a>

<a href="..\wdfmemory\ne-wdfmemory-_wdf_memory_descriptor_type.md">WDF_MEMORY_DESCRIPTOR_TYPE</a>