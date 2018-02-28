---
UID: NF:wdm.MmProbeAndLockSelectedPages
title: MmProbeAndLockSelectedPages function
author: windows-driver-content
description: The MmProbeAndLockSelectedPages routine probes the selected virtual memory pages, makes them resident, and locks them in memory.
old-location: kernel\mmprobeandlockselectedpages_.htm
old-project: kernel
ms.assetid: 1DA632FF-FD5F-4C4C-8B8E-5AC26069094A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: MmProbeAndLockSelectedPages, MmProbeAndLockSelectedPages routine [Kernel-Mode Driver Architecture], kernel.mmprobeandlockselectedpages_, wdm/MmProbeAndLockSelectedPages
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	MmProbeAndLockSelectedPages
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# MmProbeAndLockSelectedPages function
The <b>MmProbeAndLockSelectedPages</b> routine probes the selected virtual memory pages, makes them resident, and locks them in memory.

## Syntax

````
VOID MmProbeAndLockSelectedPages (
  _Inout_ PMDLX                 MemoryDescriptorList,
  _In_    PFILE_SEGMENT_ELEMENT SegmentArray,
  _In_    KPROCESSOR_MODE       AccessMode,
  _In_    LOCK_OPERATION        Operation
);
````

## Parameters

`MemoryDescriptorList`

A pointer to a memory descriptor list (MDL) that specifies a virtual memory buffer. If the routine successfully locks the pages in memory, the MDL is updated to describe the underlying physical pages.

`SegmentArray`

A pointer to an array of buffer segments that contain the virtual memory pages.

`AccessMode`

Specifies the access mode in which to probe the arguments, either KernelMode or UserMode.

`Operation`

Specifies the type of operation for which the caller wants the access rights probed and the pages locked. Set this parameter to IoReadAccess, IoWriteAccess, or IoModifyAccess. IoReadAccess indicates that the driver can examine the contents of the buffer but cannot change the contents. IoWriteAccess and IoModifyAccess, which are equivalent, indicate that the driver has both read and write access to the buffer.


## Return Value

None

## Remarks

Calls to <b>MmProbeAndLockSelectedPages</b> must be enclosed in a <b>try/except</b> block. If the pages do not support the specified operation, the routine raises the STATUS_ACCESS_VIOLATION or other exceptions. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546823">Handling Exceptions</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmProbeAndLockSelectedPages  routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>