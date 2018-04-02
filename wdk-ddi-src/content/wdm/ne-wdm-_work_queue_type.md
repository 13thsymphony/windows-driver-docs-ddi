---
UID: NE:wdm._WORK_QUEUE_TYPE
title: "_WORK_QUEUE_TYPE"
author: windows-driver-content
description: The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item.
old-location: kernel\work_queue_type.htm
old-project: kernel
ms.assetid: 5bbebf1f-ca0f-44b7-a5cd-f06b637aa3de
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: BackgroundWorkQueue, CriticalWorkQueue, CustomPriorityWorkQueue, DelayedWorkQueue, HyperCriticalWorkQueue, MaximumWorkQueue, NormalWorkQueue, RealTimeWorkQueue, SuperCriticalWorkQueue, WORK_QUEUE_TYPE, WORK_QUEUE_TYPE enumeration [Kernel-Mode Driver Architecture], _WORK_QUEUE_TYPE, kernel.work_queue_type, sysenum_5bc5bb84-a8c7-46af-982e-37b8ec51723f.xml, wdm/BackgroundWorkQueue, wdm/CriticalWorkQueue, wdm/CustomPriorityWorkQueue, wdm/DelayedWorkQueue, wdm/HyperCriticalWorkQueue, wdm/MaximumWorkQueue, wdm/NormalWorkQueue, wdm/RealTimeWorkQueue, wdm/SuperCriticalWorkQueue, wdm/WORK_QUEUE_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	WORK_QUEUE_TYPE
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# _WORK_QUEUE_TYPE Enumeration
The <b>WORK_QUEUE_TYPE</b> enumeration type indicates the type of system worker thread that handles a work item.

## Syntax
```
typedef enum _WORK_QUEUE_TYPE {
  CriticalWorkQueue        ,
  DelayedWorkQueue         ,
  HyperCriticalWorkQueue   ,
  NormalWorkQueue          ,
  BackgroundWorkQueue      ,
  RealTimeWorkQueue        ,
  SuperCriticalWorkQueue   ,
  MaximumWorkQueue         ,
  CustomPriorityWorkQueue
} WORK_QUEUE_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>CriticalWorkQueue</td>
                    <td>Indicates a real-time system worker thread. The assigned priority level is 13.</td>
                </tr>
            
                <tr>
                    <td>DelayedWorkQueue</td>
                    <td>Indicates an ordinary worker thread. The assigned priority level is 12.</td>
                </tr>
            
                <tr>
                    <td>HyperCriticalWorkQueue</td>
                    <td>System  priority level. The assigned priority level is 15.</td>
                </tr>
            
                <tr>
                    <td>NormalWorkQueue</td>
                    <td>System priority level. The assigned priority level is 8</td>
                </tr>
            
                <tr>
                    <td>BackgroundWorkQueue</td>
                    <td>System priority level. The assigned priority level is 7.</td>
                </tr>
            
                <tr>
                    <td>RealTimeWorkQueue</td>
                    <td>System  priority level. The assigned priority level is18.</td>
                </tr>
            
                <tr>
                    <td>SuperCriticalWorkQueue</td>
                    <td>System  priority level. The assigned priority level is 14.</td>
                </tr>
            
                <tr>
                    <td>MaximumWorkQueue</td>
                    <td>System  priority maximum. No priority level assigned.</td>
                </tr>
            
                <tr>
                    <td>CustomPriorityWorkQueue</td>
                    <td>The queue has a custom priority level assigned by the caller. The <b>CustomPriorityWorkQueue</b> value is the base priority level for the custom priority queue. Work items are queued at a particular priority by setting <i>QueueType</i> to <b>CustomPriorityWorkQueue</b> + <i>Priority</i> where <i>Priority</i> is the <b>KPRIORITY</b> value for the work item.

This queue type is valid starting with Windows 8.1.</td>
                </tr>
</table>

## Remarks

For drivers targeting Windows 8.1 or later versions of Windows, use of only <b>CustomPriorityWorkQueue</b> with a custom priority level is recommended.

 A work queue priority &lt; 17 is advised since queuing  
    at a higher priority may interfere with work item processing by critical system components.

For more information about system worker threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549466">IoQueueWorkItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549474">IoQueueWorkItemEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn683917">IoTryQueueWorkItem</a>