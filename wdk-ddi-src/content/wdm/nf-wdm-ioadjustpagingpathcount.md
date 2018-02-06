---
UID: NF:wdm.IoAdjustPagingPathCount
title: IoAdjustPagingPathCount macro
author: windows-driver-content
description: The IoAdjustPagingPathCount routine increments or decrements a caller-supplied page-file counter as an atomic operation.
old-location: kernel\ioadjustpagingpathcount.htm
old-project: kernel
ms.assetid: be353d10-1d8a-4fea-a415-e1729184e451
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.ioadjustpagingpathcount, IoAdjustPagingPathCount, IoAdjustPagingPathCount routine [Kernel-Mode Driver Architecture], wdm/IoAdjustPagingPathCount, k104_f52acd6d-f3f6-43c2-a339-3060a12a6298.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: wdm.h
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Wdm.h
apiname:
-	IoAdjustPagingPathCount
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoAdjustPagingPathCount function
The <b>IoAdjustPagingPathCount</b> routine increments or decrements a caller-supplied page-file counter as an atomic operation.

## Syntax

````
VOID IoAdjustPagingPathCount(
  _In_ PLONG   Count,
  _In_ BOOLEAN Increment
);
````

## Parameters

`_count_`

TBD

`_paging_`

TBD


## Return Value

None

## Remarks

This routine is useful for maintaining a count of paging files on a device. The operating system notifies a driver that a paging file has been created on, or removed from, one of the driver's devices by sending an IRP. The IRP has the major code <a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a> and the minor code <a href="https://msdn.microsoft.com/library/windows/hardware/ff550841">IRP_MN_DEVICE_USAGE_NOTIFICATION</a>.

This routine can be used for other counters, such as counters for hibernation files or crash-dump files.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | wdm.h |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550841">IRP_MN_DEVICE_USAGE_NOTIFICATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549268">IRP_MJ_PNP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAdjustPagingPathCount routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>