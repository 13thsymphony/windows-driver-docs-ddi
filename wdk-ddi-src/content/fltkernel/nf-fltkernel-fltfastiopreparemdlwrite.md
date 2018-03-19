---
UID: NF:fltkernel.FltFastIoPrepareMdlWrite
title: FltFastIoPrepareMdlWrite function
author: windows-driver-content
description: The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fltfastiopreparemdlwrite.htm
old-project: ifsk
ms.assetid: 7C48D179-35FA-44E1-B959-BD857AAA28E1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltFastIoPrepareMdlWrite, FsRtlPrepareMdlWriteDev, FsRtlPrepareMdlWriteDev routine [Installable File System Drivers], fltkernel/FsRtlPrepareMdlWriteDev, ifsk.fltfastiopreparemdlwrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Ntifs.h
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
-	FsRtlPrepareMdlWriteDev
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltFastIoPrepareMdlWrite function
The <b>FltFastIoPrepareMdlWrite</b> routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.

## Syntax

````
BOOLEAN FsRtlPrepareMdlWriteDev(
        PFLT_INSTANCE    InitiatingInstance,
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            LockKey,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````

## Parameters

`InitiatingInstance`

Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>.

`FileObject`

A pointer to the file object.

`FileOffset`

A pointer to a value that specifies the starting byte offset within the cache that holds the data.

`Length`

The length in bytes of the data to read from the cache.

`LockKey`

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked non-exclusively, the value in this parameter must be the key for that nonexclusive lock. The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.

`MdlChain`

On output, a pointer to a linked list of memory descriptor lists (MDLs) that point to the byte range within the cached data.

`IoStatus`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


## Return Value

The <b>FltFastIoPrepareMdlWrite</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.

## Remarks

<b>FltFastIoPrepareMdlWrite</b> is similar to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite~r7.md">FsRtlCopyWrite</a>, except that <b>FltFastIoPrepareMdlWrite</b> does not copy data to the cache. Instead, the physical pages that the caller will overwrite are locked in memory, and <b>FltFastIoPrepareMdlWrite</b> returns one or more memory descriptor lists (MDLs) that point to the specified byte range. The locked pages remain locked until the caller calls <a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a>. Thus each call to <b>FltFastIoPrepareMdlWrite</b> must be followed by a call to <b>FltFastIoMdlWriteComplete</b>.

The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.

Even if the call to <b>FltFastIoPrepareMdlWrite</b> fails, one or more MDLs might have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine if this has occurred. If it has, the caller must call <a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a> to free the allocated MDLs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite~r7.md">FsRtlCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>



<a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a>