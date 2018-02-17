---
UID: NF:wdm.KeGetCurrentNodeNumber
title: KeGetCurrentNodeNumber function
author: windows-driver-content
description: The KeGetCurrentNodeNumber routine gets the NUMA node number for the logical processor that the caller is running on.
old-location: kernel\kegetcurrentnodenumber.htm
old-project: kernel
ms.assetid: 9b8601ad-5605-46a3-9dbe-47dc8ed5906c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/KeGetCurrentNodeNumber, k105_08763d94-700c-4662-aebe-a8aa15a7ed4f.xml, kernel.kegetcurrentnodenumber, KeGetCurrentNodeNumber routine [Kernel-Mode Driver Architecture], KeGetCurrentNodeNumber
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Ntddk.h, Wdm.h, Ntddk.h
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
-	KeGetCurrentNodeNumber
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeGetCurrentNodeNumber function
The <b>KeGetCurrentNodeNumber</b> routine gets the NUMA node number for the logical processor that the caller is running on.

## Syntax

````
USHORT KeGetCurrentNodeNumber(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeGetCurrentNodeNumber</b> returns the node number.

## Remarks

In a non-uniform memory access (NUMA) multiprocessor architecture, a node is a collection of processors that share fast access to a region of memory. Memory access is non-uniform because a processor can access the memory in its node faster than it can access the memory in other nodes.

In a NUMA multiprocessor system that contains <i>n</i> nodes, the nodes are numbered from 0 to <i>n</i>-1. To get the highest node number (<i>n</i>-1) in the system, call the <a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Ntddk.h, Wdm.h, Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-kequeryhighestnodenumber.md">KeQueryHighestNodeNumber</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeGetCurrentNodeNumber routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>