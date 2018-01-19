---
UID : NF:ntifs.CcFastCopyRead
title : CcFastCopyRead function
author : windows-driver-content
description : The CcFastCopyRead routine performs a fast copy read from a cached file to a buffer in memory.
old-location : ifsk\ccfastcopyread.htm
old-project : ifsk
ms.assetid : 725ede16-5fc6-4465-bcdc-da7702779d68
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : CcFastCopyRead
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : CcFastCopyRead
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : < DISPATCH_LEVEL
req.typenames : TOKEN_TYPE
---


# CcFastCopyRead function
The <b>CcFastCopyRead</b> routine performs a fast copy read from a cached file to a buffer in memory.

## Syntax

````
VOID CcFastCopyRead(
  _In_  PFILE_OBJECT     FileObject,
  _In_  ULONG            FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            PageCount,
  _Out_ PVOID            Buffer,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file from which the data is to be read.

`FileOffset`

Starting byte offset within the cached file.

`Length`

Length in bytes of the data to be read.

`PageCount`

Number of pages spanned by the read.

`Buffer`

Pointer to a buffer into which the data is to be copied.

`IoStatus`

Pointer to a structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.


## Return Value

None

## Remarks

<b>CcFastCopyRead</b> is a faster version of <a href="..\ntifs\nf-ntifs-cccopyread.md">CcCopyRead</a>. It differs from <b>CcCopyRead</b> in the following respects:

<i>FileOffset</i> is a ULONG, not a PLARGE_INTEGER.

There is no <i>Wait</i> parameter. The caller must be able to enter a wait state until all the data has been copied.

<b>CcFastCopyRead</b> does not return a BOOLEAN to indicate whether the read operation was successful.

<i>FileOffset</i> plus <i>Length</i> must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, <b>CcFastCopyRead</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcFastCopyRead</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcFastCopyRead</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcFastCopyRead</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-cccopyread.md">CcCopyRead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccschedulereadahead.md">CcScheduleReadAhead</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-ccsetreadaheadgranularity.md">CcSetReadAheadGranularity</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcFastCopyRead routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>