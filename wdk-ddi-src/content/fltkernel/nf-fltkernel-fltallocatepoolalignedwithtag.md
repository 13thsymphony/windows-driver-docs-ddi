---
UID: NF:fltkernel.FltAllocatePoolAlignedWithTag
title: FltAllocatePoolAlignedWithTag function
author: windows-driver-content
description: FltAllocatePoolAlignedWithTag allocates a device-aligned buffer for use in a noncached I/O operation.
old-location: ifsk\fltallocatepoolalignedwithtag.htm
old-project: ifsk
ms.assetid: ffb1493f-6076-4b93-8431-b3ffd4679f96
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltAllocatePoolAlignedWithTag, FltAllocatePoolAlignedWithTag function [Installable File System Drivers], FltApiRef_a_to_d_b617aed0-5103-4a1e-aa0d-86247d99e803.xml, fltkernel/FltAllocatePoolAlignedWithTag, ifsk.fltallocatepoolalignedwithtag
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
req.irql: "<= APC_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	FltMgr.lib
-	FltMgr.dll
api_name:
-	FltAllocatePoolAlignedWithTag
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltAllocatePoolAlignedWithTag function
<b>FltAllocatePoolAlignedWithTag</b> allocates a device-aligned buffer for use in a noncached I/O operation.

## Syntax

````
PVOID FltAllocatePoolAlignedWithTag(
  _In_ PFLT_INSTANCE Instance,
  _In_ POOL_TYPE     PoolType,
  _In_ SIZE_T        NumberOfBytes,
  _In_ ULONG         Tag
);
````

## Parameters

`Instance`

Opaque instance pointer for a caller-owned minifilter driver instance that is attached to the volume. This parameter is required and cannot be <b>NULL</b>.

`PoolType`

Type of pool to allocate. One of the following: 

<b>NonPagedPool</b>

<b>PagedPool</b>

<b>NonPagedPoolCacheAligned</b>

<b>PagedPoolCacheAligned</b>

See <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> for a description of the available pool memory types.

`NumberOfBytes`

Number of bytes to allocate. This parameter is required and can be zero.

`Tag`

Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero.


## Return Value

If not enough free pool is available to satisfy the request, <b>FltAllocatePoolAlignedWithTag</b> returns a <b>NULL</b> pointer. Otherwise, <b>FltAllocatePoolAlignedWithTag</b> returns a pointer to the newly allocated buffer.

## Remarks

<b>FltAllocatePoolAlignedWithTag</b> allocates a buffer that is aligned in accordance with the underlying device for the given volume. Such device-aligned buffers are required for noncached I/O. (They can also be used for cached I/O.) Thus when calling routines that perform noncached I/O, such as <a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a> and <a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>, minifilter drivers should call <b>FltAllocatePoolAlignedWithTag</b> instead of <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>. 

If the caller specifies a value of zero for the <i>NumberOfBytes</i> parameter, <b>FltAllocatePoolAlignedWithTag</b> allocates the smallest amount of memory that meets the alignment requirement. 

The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. 

For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. 

When the buffer that <b>FltAllocatePoolAlignedWithTag</b> allocates is no longer needed, the caller is responsible for freeing it by calling <a href="..\fltkernel\nf-fltkernel-fltfreepoolalignedwithtag.md">FltFreePoolAlignedWithTag</a>. 

Callers of <b>FltAllocatePoolAlignedWithTag</b> can be running at IRQL DISPATCH_LEVEL only if a NonPaged<i>XxxPoolType</i> is specified. Otherwise, callers must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** | FltMgr.lib |
| **IRQL** | "<= APC_LEVEL (see Remarks section)" |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltfreepoolalignedwithtag.md">FltFreePoolAlignedWithTag</a>



<a href="..\fltkernel\nf-fltkernel-fltreadfile.md">FltReadFile</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\fltkernel\nf-fltkernel-fltwritefile.md">FltWriteFile</a>