---
UID: NE.wdm._WORK_QUEUE_TYPE
title: WORK_QUEUE_TYPE
author: windows-driver-content
description: The WORK_QUEUE_TYPE enumeration type indicates the type of system worker thread that handles a work item.
old-location: kernel\work_queue_type.htm
old-project: kernel
ms.assetid: 5bbebf1f-ca0f-44b7-a5cd-f06b637aa3de
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: WORK_QUEUE_TYPE
req.alt-loc: wdm.h
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
req.iface: 
req.product: Windows 10 or later.
---

# WORK_QUEUE_TYPE enumeration



## -description
<p>The <b>WORK_QUEUE_TYPE</b> enumeration type indicates the type of system worker thread that handles a work item.</p>


## -syntax

````
typedef enum _WORK_QUEUE_TYPE { 
  CriticalWorkQueue,
  DelayedWorkQueue,
  HyperCriticalWorkQueue,
  NormalWorkQueue,
  BackgroundWorkQueue,
  RealTimeWorkQueue,
  SuperCriticalWorkQueue,
  MaximumWorkQueue,
  CustomPriorityWorkQueue  = 32
} WORK_QUEUE_TYPE;
````


## -enum-fields
<dl>

### -field <a id="CriticalWorkQueue"></a><a id="criticalworkqueue"></a><a id="CRITICALWORKQUEUE"></a><b>CriticalWorkQueue</b>

<dd>
<p>Indicates a real-time system worker thread. The assigned priority level is 13.</p>
</dd>

### -field <a id="DelayedWorkQueue"></a><a id="delayedworkqueue"></a><a id="DELAYEDWORKQUEUE"></a><b>DelayedWorkQueue</b>

<dd>
<p>Indicates an ordinary worker thread. The assigned priority level is 12.</p>
</dd>

### -field <a id="HyperCriticalWorkQueue"></a><a id="hypercriticalworkqueue"></a><a id="HYPERCRITICALWORKQUEUE"></a><b>HyperCriticalWorkQueue</b>

<dd>
<p>System  priority level. The assigned priority level is 15.</p>
</dd>

### -field <a id="NormalWorkQueue"></a><a id="normalworkqueue"></a><a id="NORMALWORKQUEUE"></a><b>NormalWorkQueue</b>

<dd>
<p>System priority level. The assigned priority level is 8</p>
</dd>

### -field <a id="BackgroundWorkQueue"></a><a id="backgroundworkqueue"></a><a id="BACKGROUNDWORKQUEUE"></a><b>BackgroundWorkQueue</b>

<dd>
<p>System priority level. The assigned priority level is 7.</p>
</dd>

### -field <a id="RealTimeWorkQueue"></a><a id="realtimeworkqueue"></a><a id="REALTIMEWORKQUEUE"></a><b>RealTimeWorkQueue</b>

<dd>
<p>System  priority level. The assigned priority level is18.</p>
</dd>

### -field <a id="SuperCriticalWorkQueue"></a><a id="supercriticalworkqueue"></a><a id="SUPERCRITICALWORKQUEUE"></a><b>SuperCriticalWorkQueue</b>

<dd>
<p>System  priority level. The assigned priority level is 14.</p>
</dd>

### -field <a id="MaximumWorkQueue"></a><a id="maximumworkqueue"></a><a id="MAXIMUMWORKQUEUE"></a><b>MaximumWorkQueue</b>

<dd>
<p>System  priority maximum. No priority level assigned.</p>
</dd>

### -field <a id="CustomPriorityWorkQueue"></a><a id="custompriorityworkqueue"></a><a id="CUSTOMPRIORITYWORKQUEUE"></a><b>CustomPriorityWorkQueue</b>

<dd>
<p>The queue has a custom priority level assigned by the caller. The <b>CustomPriorityWorkQueue</b> value is the base priority level for the custom priority queue. Work items are queued at a particular priority by setting <i>QueueType</i> to <b>CustomPriorityWorkQueue</b> + <i>Priority</i> where <i>Priority</i> is the <b>KPRIORITY</b> value for the work item.</p>
<p>This queue type is valid starting with Windows 8.1.</p>
</dd>
</dl>

## -remarks
<p>For drivers targeting Windows 8.1 or later versions of Windows, use of only <b>CustomPriorityWorkQueue</b> with a custom priority level is recommended.</p>

<p> A work queue priority &lt; 17 is advised since queuing  
    at a higher priority may interfere with work item processing by critical system components.</p>

<p>For more information about system worker threads, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564587">System Worker Threads</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-ioqueueworkitemex.md">IoQueueWorkItemEx</a>
</dt>
<dt>
<a href="kernel.iotryqueueworkitem">IoTryQueueWorkItem</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20WORK_QUEUE_TYPE enumeration%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
