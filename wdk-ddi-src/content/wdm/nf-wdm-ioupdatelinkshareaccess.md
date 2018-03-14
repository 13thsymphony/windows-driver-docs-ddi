---
UID: NF:wdm.IoUpdateLinkShareAccess
title: IoUpdateLinkShareAccess function
author: windows-driver-content
description: The IoUpdateLinkShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location: kernel\ioupdatelinkshareaccess.htm
old-project: kernel
ms.assetid: C92E53C8-3411-4E6E-B48E-B16F6B815488
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: IoUpdateLinkShareAccess, IoUpdateLinkShareAccess function [Kernel-Mode Driver Architecture], kernel.ioupdatelinkshareaccess, wdm/IoUpdateLinkShareAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoUpdateLinkShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoUpdateLinkShareAccess function
The <b>IoUpdateLinkShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.

## Syntax

````
VOID IoUpdateLinkShareAccess(
  _In_        PFILE_OBJECT       FileObject,
  _Inout_     PSHARE_ACCESS      ShareAccess,
  _Inout_opt_ PLINK_SHARE_ACCESS LinkShareAccess
);
````

## Parameters

`FileObject`

Pointer to the file object, which usually is being closed by the current thread.

`ShareAccess`

Pointer to the share-access structure that describes how the open file object is currently being accessed.

`LinkShareAccess`

Pointer to the share-access structure that describes how the open file object is currently being accessed.


## Return Value

None

## Remarks

<b>IoUpdateLinkShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoUpdateLinkShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Before calling <b>IoUpdateLinkShareAccess</b>, the caller must successfully call <a href="..\wdm\nf-wdm-iochecklinkshareaccess.md">IoCheckLinkShareAccess</a> with <i>Update</i> set to False. Such a call to <b>IoCheckLinkShareAccess</b> determines whether the requested shared access is compatible with the way the file object is currently being accessed by other opens, but it does not update the <b>SHARE_ACCESS</b> structure. <b>IoUpdateLinkShareAccess</b> actually updates the <b>SHARE_ACCESS</b> structure associated with the file object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\nf-wdm-iochecklinkshareaccess.md">IoCheckLinkShareAccess</a>



<a href="..\wdm\nf-wdm-ioremovelinkshareaccess.md">IoRemoveLinkShareAccess</a>



<a href="..\wdm\nf-wdm-iosetlinkshareaccess.md">IoSetLinkShareAccess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoUpdateLinkShareAccess function%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>