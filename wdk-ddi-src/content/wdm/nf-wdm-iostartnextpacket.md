---
UID: NF.wdm.IoStartNextPacket
title: IoStartNextPacket
author: windows-driver-content
description: The IoStartNextPacket routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's StartIo routine.
old-location: kernel\iostartnextpacket.htm
old-project: kernel
ms.assetid: f1197dfd-03d7-4ac2-8f11-60da413e32b2
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: IoStartNextPacket
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
req.alt-api: IoStartNextPacket
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlDispatch, SpinLockSafe, StartIoRecursion, HwStorPortProhibitedDDIs, IrqlDispatch(storport), SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: DISPATCH_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# IoStartNextPacket function



## -description
<p>The <b>IoStartNextPacket</b> routine dequeues the next IRP, if any, from the given device object's associated device queue and calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff563858">StartIo</a> routine.</p>


## -syntax

````
VOID IoStartNextPacket(
  _In_ PDEVICE_OBJECT DeviceObject,
  _In_ BOOLEAN        Cancelable
);
````


## -parameters
<dl>

### -param <i>DeviceObject</i> [in]

<dd>
<p>Pointer to the device object for which the IRP is to be dequeued.</p>
</dd>

### -param <i>Cancelable</i> [in]

<dd>
<p>Specifies whether IRPs in the device queue can be canceled. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If there are no IRPs currently in the device queue for the target <i>DeviceObject</i>, this routine simply returns control to the caller.</p>

<p>If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable </i>is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. </p>

<p>Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacket</b>.</p>

<p>Drivers that call <b>IoStartNextPacket </b>from their <i>StartIo</i> routine should be aware of recursion issues. If a driver can call <b>IoStartNextPacket</b> on a large number of requests in succession from its <i>StartIo</i> routine (for example, when a device error occurs and the driver is clearing out it device queue), you should set the <i>DeferredStartIo</i> attribute for the device by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a> routine. This attribute ensures that the next packet will not be issued until the previous <i>StartIo</i> call returns.</p>

<p>Callers of <b>IoStartNextPacket</b> must be running at IRQL = DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.</p>

<p>If there are no IRPs currently in the device queue for the target <i>DeviceObject</i>, this routine simply returns control to the caller.</p>

<p>If the driver passed a pointer to a cancel routine when it called <b>IoStartPacket</b>, it should pass <b>TRUE</b> in the <i>Cancelable</i> parameter. If <i>Cancelable </i>is <b>TRUE</b>, the I/O manager will use the cancel spin lock to protect the device queue and the current IRP. </p>

<p>Drivers that do not have a <i>StartIo</i> routine cannot call <b>IoStartNextPacket</b>.</p>

<p>Drivers that call <b>IoStartNextPacket </b>from their <i>StartIo</i> routine should be aware of recursion issues. If a driver can call <b>IoStartNextPacket</b> on a large number of requests in succession from its <i>StartIo</i> routine (for example, when a device error occurs and the driver is clearing out it device queue), you should set the <i>DeferredStartIo</i> attribute for the device by using <a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a> routine. This attribute ensures that the next packet will not be issued until the previous <i>StartIo</i> call returns.</p>

<p>Callers of <b>IoStartNextPacket</b> must be running at IRQL = DISPATCH_LEVEL. Usually, this routine is called from a device driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff544079">DpcForIsr</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> routine, both of which are run at IRQL = DISPATCH_LEVEL.</p>

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
<p>DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547743">IrqlDispatch</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454252">SpinLockSafe</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff552798">StartIoRecursion</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_irqldispatch">IrqlDispatch(storport)</a>, <a href="devtest.storport_spinlocksafe">SpinLockSafe(storport)</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550330">IoSetStartIoAttributes</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550363">IoStartNextPacketByKey</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff550370">IoStartPacket</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoStartNextPacket routine%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
