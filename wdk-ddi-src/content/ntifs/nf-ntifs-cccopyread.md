---
UID: NF:ntifs.CcCopyRead
title: CcCopyRead function
author: windows-driver-content
description: The CcCopyRead routine copies data from a cached file to a user buffer.
old-location: ifsk\cccopyread.htm
old-project: ifsk
ms.assetid: ab095bc4-b896-4c8b-a778-714952fd41d4
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/CcCopyRead, ifsk.cccopyread, ccref_76dde6ff-ccd7-4d90-a744-9d2c05624b00.xml, CcCopyRead, CcCopyRead routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later Windows operating systems.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcCopyRead
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcCopyRead function
The <b>CcCopyRead</b> routine copies data from a cached file to a user buffer.

## Syntax

````
BOOLEAN CcCopyRead(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  BOOLEAN          Wait,
  _Out_ PVOID            Buffer,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````

## Parameters

`FileObject`

A pointer to a file object for the cached file from which the data is to be read.

`FileOffset`

A pointer to a variable that specifies the starting byte offset within the cached file.

`Length`

The length in bytes of the data to be read.

`Wait`

Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.

`Buffer`

A pointer to a buffer into which the data is to be copied.

`IoStatus`

A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, <i>IoStatus.Information</i> contains the actual number of bytes that were copied.


## Return Value

The <b>CcCopyRead</b> routine returns <b>TRUE</b> if the data was copied successfully, <b>FALSE</b> otherwise.

## Remarks

If <i>Wait</i> is <b>TRUE</b>, <b>CcCopyRead</b> is guaranteed to complete the copy request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>CcCopyRead</b> will refuse to block, and will return <b>FALSE</b>, if the required pages of the cached file are not already resident in memory. 

<i>FileOffset</i> plus <i>Length</i> must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, <b>CcCopyRead</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcCopyRead</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcCopyRead</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcCopyRead</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Microsoft Windows 2000 and later Windows operating systems. Available on Microsoft Windows 2000 and later Windows operating systems. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-ccschedulereadahead.md">CcScheduleReadAhead</a>

<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>

<a href="..\ntifs\nf-ntifs-ccsetreadaheadgranularity.md">CcSetReadAheadGranularity</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>

<a href="..\ntifs\nf-ntifs-ccfastcopyread.md">CcFastCopyRead</a>

<a href="..\ntifs\nf-ntifs-ccsetadditionalcacheattributes.md">CcSetAdditionalCacheAttributes</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCopyRead routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>