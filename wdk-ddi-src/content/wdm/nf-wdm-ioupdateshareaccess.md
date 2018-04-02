---
UID: NF:wdm.IoUpdateShareAccess
title: IoUpdateShareAccess function
author: windows-driver-content
description: The IoUpdateShareAccess routine updates the share access for the given file object, usually when the file is being opened.
old-location: kernel\ioupdateshareaccess.htm
old-project: kernel
ms.assetid: b8e14607-a8d4-4e15-8b1d-92096879ea65
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IoUpdateShareAccess, IoUpdateShareAccess routine [Kernel-Mode Driver Architecture], k104_24b78a73-20f1-4d8b-be0e-67964e8dbc31.xml, kernel.ioupdateshareaccess, wdm/IoUpdateShareAccess
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	IoUpdateShareAccess
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoUpdateShareAccess function
The <b>IoUpdateShareAccess</b> routine updates the share access for the given file object, usually when the file is being opened.

## Syntax

```
NTKERNELAPI VOID IoUpdateShareAccess(
  PFILE_OBJECT  FileObject,
  PSHARE_ACCESS ShareAccess
);
```

## Parameters

`FileObject`

Pointer to a referenced file object representing the file or associated device object for which to update the share access.

`ShareAccess`

Pointer to the common <b>SHARE_ACCESS</b> structure associated with the <i>FileObject</i>. Drivers should treat this structure as opaque.


## Return Value

None

## Remarks

<b>IoUpdateShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoUpdateShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

Before calling <b>IoUpdateShareAccess</b>, the caller must successfully call <b>IoCheckShareAccess</b> with <i>Update</i> set to False. Such a call to <b>IoCheckShareAccess</b> determines whether the requested shared access is compatible with the way the file object is currently being accessed by other opens, but it does not update the <b>SHARE_ACCESS</b> structure. <b>IoUpdateShareAccess</b> actually updates the <b>SHARE_ACCESS</b> structure associated with the file object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | IrqlIoPassive5, PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff548341">IoCheckShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549587">IoRemoveShareAccess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550324">IoSetShareAccess</a>