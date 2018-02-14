---
UID: NF:wdm.IoRemoveShareAccess
title: IoRemoveShareAccess function
author: windows-driver-content
description: The IoRemoveShareAccess routine removes the access and share-access information for a given open instance of a file object.
old-location: kernel\ioremoveshareaccess.htm
old-project: kernel
ms.assetid: 999ee9cc-13c7-4e6b-a294-7e7d28272384
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k104_0034e41b-0320-40e0-8dea-847db6b6dc58.xml, kernel.ioremoveshareaccess, IoRemoveShareAccess routine [Kernel-Mode Driver Architecture], wdm/IoRemoveShareAccess, IoRemoveShareAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoRemoveShareAccess
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoRemoveShareAccess function
The <b>IoRemoveShareAccess</b> routine removes the access and share-access information for a given open instance of a file object.

## Syntax

````
VOID IoRemoveShareAccess(
  _In_    PFILE_OBJECT  FileObject,
  _Inout_ PSHARE_ACCESS ShareAccess
);
````

## Parameters

`FileObject`

Pointer to the file object, which usually is being closed by the current thread.

`ShareAccess`

Pointer to the share-access structure that describes how the open file object is currently being accessed.


## Return Value

None

## Remarks

This routine is a reciprocal to <a href="..\wdm\nf-wdm-ioupdateshareaccess.md">IoUpdateShareAccess</a>.

<b>IoRemoveShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoRemoveShareAccess</b> by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Callers of <b>IoRemoveShareAccess</b> must be running at IRQL = PASSIVE_LEVEL and in the context of the thread that requested that the <i>FileObject</i> be closed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |
| **DDI compliance rules** | IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-ioupdateshareaccess.md">IoUpdateShareAccess</a>



<a href="..\wdm\nf-wdm-iosetshareaccess.md">IoSetShareAccess</a>



<a href="..\wdm\nf-wdm-iocheckshareaccess.md">IoCheckShareAccess</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRemoveShareAccess routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>