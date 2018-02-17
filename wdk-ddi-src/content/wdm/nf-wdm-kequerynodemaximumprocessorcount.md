---
UID: NF:wdm.KeQueryNodeMaximumProcessorCount
title: KeQueryNodeMaximumProcessorCount function
author: windows-driver-content
description: The KeQueryNodeMaximumProcessorCount routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain.
old-location: kernel\kequerynodemaximumprocessorcount.htm
old-project: kernel
ms.assetid: 56688002-d481-45a6-bfb0-e7761f9ae055
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k105_15c5df15-b04a-41bd-9aec-2e402e2824a9.xml, KeQueryNodeMaximumProcessorCount, kernel.kequerynodemaximumprocessorcount, KeQueryNodeMaximumProcessorCount routine [Kernel-Mode Driver Architecture], wdm/KeQueryNodeMaximumProcessorCount
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeQueryNodeMaximumProcessorCount
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeQueryNodeMaximumProcessorCount function
The <b>KeQueryNodeMaximumProcessorCount</b> routine returns the maximum number of logical processors that a specified node in a non-uniform memory access (NUMA) multiprocessor system can contain.

## Syntax

````
USHORT KeQueryNodeMaximumProcessorCount(
  _In_ USHORT NodeNumber
);
````

## Parameters

`NodeNumber`

The node number. If a NUMA multiprocessor system contains <i>n</i> nodes, valid node numbers are in the range 0 to <i>n</i>-1. To get the highest node number (<i>n</i>-1) in the system, call the <a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine.


## Return Value

<b>KeQueryNodeMaximumProcessorCount</b> returns the maximum number of logical processors.

## Remarks

In a multiprocessor system with a NUMA architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

The count returned by this routine includes any logical processors that can be dynamically added to the node while the multiprocessor system is running.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryNodeMaximumProcessorCount routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>