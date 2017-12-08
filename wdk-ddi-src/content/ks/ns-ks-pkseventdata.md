---
UID: NS.KS.PKSEVENTDATA
title: PKSEVENTDATA
author: windows-driver-content
description: Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.
old-location: stream\kseventdata.htm
old-project: stream
ms.assetid: 83503353-e4f7-47ba-9a0c-71264798e983
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PKSEVENTDATA, KSEVENTDATA, *PKSEVENTDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSEVENTDATA
req.alt-loc: ks.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# PKSEVENTDATA structure



## -description
Kernel streaming clients send the KSEVENTDATA structure to the class driver to specify a notification method.


## -syntax

````
typedef struct {
  ULONG NotificationType;
  union {
    struct {
      HANDLE    Event;
      ULONG_PTR Reserved[2];
    } EventHandle;
    struct {
      HANDLE Semaphore;
      ULONG  Reserved;
      LONG   Adjustment;
    } SemaphoreHandle;
    struct {
      PVOID    Unused;
      LONG_PTR Alignment[2];
    } Alignment;
  };
} KSEVENTDATA, *PKSEVENTDATA;
````


## -struct-fields

### -field NotificationType

Contains flags indicating what type of notification should be performed. The following table lists all the possible values for the NotificationType member.
<table>
<tr>
<th>NotificationType Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
KSEVENTF_EVENT_HANDLE
</td>
<td>
Indicates that a Win32 synchronization or notification object handle is being passed. The KSEVENTDATA.EventHandle.Event element contains the handle.
</td>
</tr>
<tr>
<td>
KSEVENTF_SEMAPHORE_HANDLE
</td>
<td>
Indicates that a Win32 semaphore handle is being passed. The KSEVENTDATA.SemaphoreHandle.Semaphore element contains the handle.
</td>
</tr>
<tr>
<td>
KSEVENTF_EVENT_OBJECT
</td>
<td>
Indicates that a pointer to a kernel synchronization or notification object is being passed. The KSEVENTDATA.EventObject.Event element contains a pointer to this object. This is available only to kernel-mode clients.
</td>
</tr>
<tr>
<td>
KSEVENTF_SEMAPHORE_OBJECT
</td>
<td>
Indicates that a pointer to a kernel semaphore object is being passed. The KSEVENTDATA.SemaphoreObject.Semaphore element contains a pointer to this object. This is available only to kernel-mode clients.
</td>
</tr>
<tr>
<td>
KSEVENTF_DPC
</td>
<td>
Indicates that a pointer to a kernel DPC structure is being passed. The KSEVENTDATA.Dpc.Dpc element contains a pointer to the DPC. This is available only to kernel-mode clients.
</td>
</tr>
<tr>
<td>
KSEVENTF_WORKITEM
</td>
<td>
Indicates that a pointer to a kernel work item structure is being passed. The KSEVENTDATA.WorkItem.WorkQueueItem contains a pointer to the work item. This is available only to kernel-mode clients.
</td>
</tr>
<tr>
<td>
KSEVENTF_KSWORKITEM
</td>
<td>
Indicates that a pointer to a kernel streaming work item structure is being passed. The KSEVENTDATA.KsWorkItem.WorkQueueItem contains a pointer to the work item, and is queued to a previously registered kernel streaming work item. This is available only to kernel-mode clients.
</td>
</tr>
</table>
 

### -field EventHandle


### -field Event

Contains a handle to a synchronization event when the KSEVENT_EVENT_HANDLE flag is set.

### -field Reserved

Reserved and set to zero.
</dd>
</dl>

### -field SemaphoreHandle


### -field Semaphore

Contains a handle to a semaphore when the KSEVENT_SEMAPHORE_HANDLE flag is set.

### -field Reserved

Reserved and set to zero.

### -field Adjustment

Contains the adjustment to the semaphore when it is released.
</dd>
</dl>

### -field Alignment


### -field Unused

Not used.

### -field Alignment

Reserved for internal use by AVStream. Minidrivers should not manipulate this member.
</dd>
</dl>

## -remarks
For more information, see <a href="https://msdn.microsoft.com/3eaa1d65-8417-4a07-b358-823394baec9b">KS Events</a>.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a>
</dt>
<dt>
<a href="stream.ksevent">KSEVENT</a>
</dt>
<dt>
<a href="ifsk.work_queue_item">WORK_QUEUE_ITEM</a>
</dt>
<dt>
<a href="kernel.work_queue_type">WORK_QUEUE_TYPE</a>
</dt>
<dt>
<a href="stream.ksincrementcountedworker">KsIncrementCountedWorker</a>
</dt>
<dt>
<a href="stream.ksregisterworker">KsRegisterWorker</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSEVENTDATA structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
