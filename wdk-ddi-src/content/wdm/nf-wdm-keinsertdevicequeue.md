---
UID: NF.wdm.KeInsertDeviceQueue
title: KeInsertDeviceQueue
author: windows-driver-content
description: The KeInsertDeviceQueue routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.
old-location: kernel\keinsertdevicequeue.htm
old-project: kernel
ms.assetid: d0e634e0-f0b4-49a7-9df5-7af0842154f4
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: KeInsertDeviceQueue
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
req.alt-api: KeInsertDeviceQueue
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

# KeInsertDeviceQueue function



## -description
<p>The <b>KeInsertDeviceQueue</b> routine acquires the spin lock for the specified device queue object and, if the device queue is set to a busy state, queues the specified entry.</p>


## -syntax

````
BOOLEAN KeInsertDeviceQueue(
  _Inout_ PKDEVICE_QUEUE       DeviceQueue,
  _Inout_ PKDEVICE_QUEUE_ENTRY DeviceQueueEntry
);
````


## -parameters
<dl>

### -param <i>DeviceQueue</i> [in, out]

<dd>
<p>Pointer to a control object of type device queue for which the caller provides the storage.</p>
</dd>

### -param <i>DeviceQueueEntry</i> [in, out]

<dd>
<p>Pointer to the device queue entry that is to be inserted. </p>
</dd>
</dl>

## -returns
<p>If the device queue is empty, <b>FALSE</b> is returned and the <i>DeviceQueueEntry</i> is not inserted in the device queue.</p>

## -remarks
<p>If the device queue is set to a busy state, the specified <i>DeviceQueueEntry</i> is inserted at the tail of the device queue and the device queue spin lock is released.</p>

<p>If <b>KeInsertDeviceQueue</b> returns <b>FALSE</b>, the entry was not queued and the caller must begin processing the IRP. A call to <b>KeInsertDeviceQueue</b> or <a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a> when the queue is empty causes the device queue to change from a not-busy state to a busy state.</p>

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
<a href="..\wdm\nf-wdm-keinsertbykeydevicequeue.md">KeInsertByKeyDeviceQueue</a>
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
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInsertDeviceQueue routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
