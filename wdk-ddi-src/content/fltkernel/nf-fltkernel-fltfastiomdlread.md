---
UID: NF:fltkernel.FltFastIoMdlRead
title: FltFastIoMdlRead function
author: windows-driver-content
description: The FltFastIoMdlRead routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.
old-location: ifsk\fltfastiomdlread.htm
old-project: ifsk
ms.assetid: 1DF810B5-D4C3-4F67-B913-C2B2132DFDE2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: FltFastIoMdlRead, FsRtlMdlReadDev, FsRtlMdlReadDev routine [Installable File System Drivers], fltkernel/FsRtlMdlReadDev, ifsk.fltfastiomdlread
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
-	FsRtlMdlReadDev
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# FltFastIoMdlRead function
The <b>FltFastIoMdlRead</b> routine returns a memory descriptor list (MDL) that points directly to the specified byte range in the file cache.

## Syntax

````
BOOLEAN FsRtlMdlReadDev(
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

A pointer to a file object for the cached file.

`FileOffset`

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.

`Length`

The length in bytes of the data to read from the cache.

`LockKey`

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked non-exclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.

`MdlChain`

On output, a pointer to a linked list of memory descriptor lists (MDLs).

`IoStatus`

A pointer to an <a href="..\wudfwdm\ns-wudfwdm-_io_status_block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


## Return Value

The <b>FltFastIoMdlRead</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.

## Remarks

The <b>FltFastIoMdlRead</b> routine bypasses the usual IRP mechanism and returns a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read.

The routine is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a> and <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md">FsRtlMdlReadDev</a>. <b>FltFastIoMdlRead</b>, <b>CcMdlRead</b>, and <b>FsRtlMdlReadDev</b> lock the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <a href="..\fltkernel\nf-fltkernel-fltfastiomdlreadcomplete.md">FltFastIoMdlReadComplete</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | fltkernel.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlmdlreaddev~r6.md">FsRtlMdlReadDev</a>



<a href="..\fltkernel\nf-fltkernel-fltfastiomdlreadcomplete.md">FltFastIoMdlReadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFastIoMdlRead routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>