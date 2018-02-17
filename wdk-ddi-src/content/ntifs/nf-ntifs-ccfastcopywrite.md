---
UID: NF:ntifs.CcFastCopyWrite
title: CcFastCopyWrite function
author: windows-driver-content
description: The CcFastCopyWrite routine performs a fast copy write from a buffer in memory to a cached file.
old-location: ifsk\ccfastcopywrite.htm
old-project: ifsk
ms.assetid: 414d0b36-d7c2-4a01-8ceb-3817a11c422c
ms.author: windowsdriverdev
ms.date: 2/7/2018
ms.keywords: CcFastCopyWrite routine [Installable File System Drivers], ccref_f5763242-c6f6-4638-8577-a6c65001a8ca.xml, ntifs/CcFastCopyWrite, CcFastCopyWrite, ifsk.ccfastcopywrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	CcFastCopyWrite
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# CcFastCopyWrite function
The <b>CcFastCopyWrite</b> routine performs a fast copy write from a buffer in memory to a cached file.

## Syntax

````
VOID CcFastCopyWrite(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        FileOffset,
  _In_ ULONG        Length,
  _In_ PVOID        Buffer
);
````

## Parameters

`FileObject`

Pointer to a file object for the cached file to which the data is to be written.

`FileOffset`

Pointer to a variable that specifies the starting byte offset within the cached file.

`Length`

Length in bytes of the data to be written.

`Buffer`

Pointer to the buffer from which the data is to be copied.


## Return Value

None

## Remarks

<b>CcFastCopyWrite</b> is a faster version of <a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>. It differs from <b>CcCopyWrite</b> in the following respects:

<ul>
<li>
<i>FileOffset</i> is a ULONG, not a PLARGE_INTEGER.

</li>
<li>
There is no <i>Wait</i> parameter. The caller must be able to enter a wait state until all the data has been copied.

</li>
<li>
<b>CcFastCopyWrite</b> does not return a BOOLEAN to indicate whether the write operation was successful.

</li>
</ul>
If the required pages of the cached file are already resident in memory, the data is copied immediately and no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be copied.

If any failure occurs, <b>CcFastCopyWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcFastCopyWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcFastCopyWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcFastCopyWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |

## See Also

<a href="..\ntifs\nf-ntifs-cccopywrite.md">CcCopyWrite</a>



<a href="..\ntifs\nf-ntifs-ccinitializecachemap.md">CcInitializeCacheMap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcFastCopyWrite routine%20 RELEASE:%20(2/7/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>