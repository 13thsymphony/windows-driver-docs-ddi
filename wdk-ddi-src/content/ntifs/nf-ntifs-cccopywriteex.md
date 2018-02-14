---
UID: NF:ntifs.CcCopyWriteEx
title: CcCopyWriteEx function
author: windows-driver-content
description: The CcCopyWriteEx routine copies data from a user buffer to a cached file. The I/O byte count for the operation is charged to the issuing thread.
old-location: ifsk\cccopywriteex.htm
old-project: ifsk
ms.assetid: A8945F1C-56CF-494F-9E50-11C7A713E5F0
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: CcCopyWriteEx, ifsk.cccopywriteex, CcCopyWriteEx routine [Installable File System Drivers], ntifs/CcCopyWriteEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
-	CcCopyWriteEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcCopyWriteEx function
The <b>CcCopyWriteEx</b> routine copies data from a user buffer to a cached file. The I/O byte count for the operation is charged to the issuing thread.

## Syntax

````
BOOLEAN CcCopyWriteEx(
  _In_ PFILE_OBJECT   FileObject,
  _In_ PLARGE_INTEGER FileOffset,
  _In_ ULONG          Length,
  _In_ BOOLEAN        Wait,
  _In_ PVOID          Buffer,
  _In_ PETHREAD       IoIssuerThread
);
````

## Parameters

`FileObject`

A pointer to a file object for the cached file to which the data is to be written.

`FileOffset`

A pointer to a variable that specifies the starting byte offset within the cached file.

`Length`

The length in bytes of the data to be written.

`Wait`

Set to <b>TRUE</b> if the caller can be put into a wait state until all the data has been copied, <b>FALSE</b> otherwise.

`Buffer`

A pointer to the buffer from which the data is to be copied.

`IoIssuerThread`

The thread issuing the write request. For a file system with disk I/O accounting enabled, this is the thread the I/O is charged to. If <i>IoIssuerThread</i> is NULL, the I/O is charged to the current thread.


## Return Value

The <b>CcCopyWriteEx</b> routine returns <b>TRUE</b> if the data was copied successfully, <b>FALSE</b> otherwise.

## Remarks

If <i>Wait</i> is <b>TRUE</b>, <b>CcCopyWriteEx</b> is guaranteed to complete the copy request and return <b>TRUE</b>. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If <i>Wait</i> is <b>FALSE</b>, <b>CcCopyWriteEx</b> will refuse to block, and will return <b>FALSE</b>, if the required pages of the cached file are not already resident in memory or if the FO_WRITE_THROUGH flag is set on the file object.

If any failure occurs, <b>CcCopyWriteEx</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcCopyWriteEx</b> raises an exception with the <b>STATUS_INSUFFICIENT_RESOURCES</b> status; if an I/O error occurs, <b>CcCopyWriteEx</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcCopyWriteEx</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h, FltKernel.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcCopyWriteEx routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>