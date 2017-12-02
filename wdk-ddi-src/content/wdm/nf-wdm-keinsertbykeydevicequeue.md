---
UID: NF.wdm.KeInsertByKeyDeviceQueue
title: KeInsertByKeyDeviceQueue
author: windows-driver-content
description: The KeInsertByKeyDeviceQueue routine acquires the spin lock for the specified DeviceQueue and queues an entry according to the specified sort-key value if the device queue is set to a busy state.
old-location: kernel\keinsertbykeydevicequeue.htm
old-project: kernel
ms.assetid: fa395673-108f-4cf0-b05f-a160aa0b02ea
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KeInsertByKeyDeviceQueue
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
req.alt-api: KeInsertByKeyDeviceQueue
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlDispatch, MarkingQueuedIrps, HwStorPortProhibitedDDIs, IrqlDispatch(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# KeInsertByKeyDeviceQueue function



## -description
<p>The <b>KeInsertByKeyDeviceQueue</b> routine acquires the spin lock for the specified <i>DeviceQueue</i> and queues an entry according to the specified sort-key value if the device queue is set to a busy state.</p>


## -syntax

````
BOOLEAN KeInsertByKeyDeviceQueue(
  _Inout_ PKDEVICE_QUEUE       DeviceQueue,
  _Inout_ PKDEVICE_QUEUE_ENTRY DeviceQueueEntry,
  _In_    ULONG                SortKey
);
````


## -parameters
<dl>

### -param DeviceQueue [in, out]

<dd>
<p>Pointer to a control object of the device queue type for which the caller provides the storage.</p>
</dd>

### -param DeviceQueueEntry [in, out]

<dd>
<p>Pointer to the device queue entry to be inserted into the device queue according to the specific key value.</p>
</dd>

### -param SortKey [in]

<dd>
<p>Specifies the sort-key value that determines the position in the device queue in which to insert the entry. </p>
</dd>
</dl>

## -returns
<p>If the device queue is empty, <b>FALSE</b> is returned, meaning the <i>DeviceQueueEntry</i> is not inserted in the device queue.</p>

## -remarks
<p>The specified device queue spin lock is acquired and the state of the device queue is checked. If the device queue is set to a busy state, the IRP specified by the <i>DeviceQueueEntry</i> is inserted into the device queue according to its sort key value and the device queue spin lock is released.</p>

<p>The new entry is positioned in the device queue after any entries in the queue with sort key values less than or equal to its sort key value and preceding any entries with sort key values that are greater.</p>

<p>If <b>KeInsertByKeyDeviceQueue</b> returns <b>FALSE</b>, the caller must begin processing the IRP. A call to <a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a> or <b>KeInsertByKeyDeviceQueue</b> when the queue is empty causes the device queue to transition from a not-busy state to a busy state.</p>

<p>This routine is for code that queues an I/O request to a device driver. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
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
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_irqldispatch">IrqlDispatch</a>, <a href="devtest.wdm_markingqueuedirps">MarkingQueuedIrps</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_irqldispatch">IrqlDispatch(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keinitializedevicequeue.md">KeInitializeDeviceQueue</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keinsertdevicequeue.md">KeInsertDeviceQueue</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keremovedevicequeue.md">KeRemoveDeviceQueue</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-keremoveentrydevicequeue.md">KeRemoveEntryDeviceQueue</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInsertByKeyDeviceQueue routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
