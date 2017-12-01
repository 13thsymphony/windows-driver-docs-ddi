---
UID: NI.pmi.IOCTL_PMI_REGISTER_EVENT_NOTIFY
title: IOCTL_PMI_REGISTER_EVENT_NOTIFY
author: windows-driver-content
description: The IOCTL_PMI_REGISTER_EVENT_NOTIFY request registers the IOCTL initiator to be notified about a power meter event. When the event occurs, the Power Meter Interface (PMI) completes the IOCTL request and returns information about the event.
old-location: powermeter\ioctl_pmi_register_event_notify.htm
old-project: powermeter
ms.assetid: 0d79a25b-846d-490d-9e04-d319fa860761
ms.author: windowsdriverdev
ms.date: 11/6/2017
ms.keywords: PEP_WORK_IDLE_STATE, PEP_WORK_IDLE_STATE, *PPEP_WORK_IDLE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_PMI_REGISTER_EVENT_NOTIFY
req.alt-loc: Pmi.h
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
req.iface: 
---

# IOCTL_PMI_REGISTER_EVENT_NOTIFY IOCTL



## -description
<p>The <b>IOCTL_PMI_REGISTER_EVENT_NOTIFY</b> request registers the IOCTL initiator to be notified about a power meter event. When the event occurs, the Power Meter Interface (PMI) completes the IOCTL request and returns information about the event.</p>


## -ioctlparameters

### -input-buffer
<p>The <b>AssociatedIrp.SystemBuffer</b> member of the I/O request packet (IRP) points to an initiator-allocated input buffer that contains a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

### -input-buffer-length
<p>The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IRP's current I/O stack location (<a href="..\wdm\ns-wdm--io-stack-location.md">IO_STACK_LOCATION</a>) is set to the size in bytes of the input buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. This size must be greater than or equal to <b>sizeof</b>(<b>PMI_EVENT</b>) or the request will fail with an error status of STATUS_BUFFER_TOO_SMALL.</p>

<p>The <b>Parameters.DeviceIoControl.InputBufferLength</b> member of the IRP's current I/O stack location (<a href="..\wdm\ns-wdm--io-stack-location.md">IO_STACK_LOCATION</a>) is set to the size in bytes of the input buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member. This size must be greater than or equal to <b>sizeof</b>(<b>PMI_EVENT</b>) or the request will fail with an error status of STATUS_BUFFER_TOO_SMALL.</p>

### -output-buffer
<p>None.</p>

<p>None.</p>

<p>None.</p>

### -output-buffer-length
<p>None.</p>

<p>None.</p>

<p>None.</p>

<p>None.</p>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<p>The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

<p>The <b>Status</b> member is set to one of the following values:</p>

<p></p>

<p>The WDM driver that supports the PMI interface has completed the IOCTL request successfully.</p>

<p>The WDM driver that supports the PMI interface has put the IOCTL request in a queue and will complete it after a PMI event occurs. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a> is less than the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure. </p>

<p>The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

<p>The <b>Status</b> member is set to one of the following values:</p>

<p></p>

<p>The WDM driver that supports the PMI interface has completed the IOCTL request successfully.</p>

<p>The WDM driver that supports the PMI interface has put the IOCTL request in a queue and will complete it after a PMI event occurs. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a> is less than the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure. </p>

<p>The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

<p>The <b>Status</b> member is set to one of the following values:</p>

<p></p>

<p>The WDM driver that supports the PMI interface has completed the IOCTL request successfully.</p>

<p>The WDM driver that supports the PMI interface has put the IOCTL request in a queue and will complete it after a PMI event occurs. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a> is less than the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure. </p>

<p>The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

<p>The <b>Status</b> member is set to one of the following values:</p>

<p></p>

<p>The WDM driver that supports the PMI interface has completed the IOCTL request successfully.</p>

<p>The WDM driver that supports the PMI interface has put the IOCTL request in a queue and will complete it after a PMI event occurs. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a> is less than the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure. </p>

<p>The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure.</p>

<p>The <b>Status</b> member is set to one of the following values:</p>

<p></p>

<p>The WDM driver that supports the PMI interface has completed the IOCTL request successfully.</p>

<p>The WDM driver that supports the PMI interface has put the IOCTL request in a queue and will complete it after a PMI event occurs. </p>

<p>The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a> is less than the size, in bytes, of a <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure. </p>

## -remarks
<p>PMI creates an event notification queue for each initiator that opens the device instance for a power meter by using the <a href="fs.createfile">CreateFile</a> function. A separate queue is created for each caller's connection to a device instance. The following points apply to the event notification queue:</p>

<p>When PMI creates the event notification queue, the queue is empty. After the queue is created, PMI sends events to the caller after the caller has registered for event notification by using the <b>IOCTL_PMI_REGISTER_EVENT_NOTIFY</b> request. </p>

<p>If the event notification queue is empty when the caller registers, the <b>IOCTL_PMI_REGISTER_EVENT_NOTIFY</b> request remains pending until either an event occurs or the device instance connection is broken through the <b>CloseFile</b> function.</p>

<p>After the event notification queue is created, the queue will contain unsent events for the caller. This prevents callers from missing events during the interval between when the driver processes one event and the caller registers for another. If there are events in the caller's queue, they are sent immediately after the caller registers by using an <b>IOCTL_PMI_REGISTER_EVENT_NOTIFY</b> request.</p>

<p>When PMI sends a power meter event to the caller, it completes the <b>IOCTL_PMI_REGISTER_EVENT_NOTIFY</b> request. The data that describes the event is contained within the <a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a> structure in the output buffer that is referenced by the <b>MdlAddress</b> member of the <a href="..\ntifs\ns-ntifs--irp.md">IRP</a>. The <b>EventType </b>member of this structure contains information about the power meter event's type. For example, if <b>EventType</b> is set to <b>PmiConfigurationChangedEvent</b>, the power meter's configuration has changed. In this case, the caller can query the power meter's new configuration by using an <a href="..\pmi\ni-pmi-ioctl-pmi-get-configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> request.</p>

<p>For more information about the <a href="fs.createfile">CreateFile</a> and <b>CloseFile</b> functions, refer to the Windows SDK documentation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Pmi.h (include Pmi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\pmi\ni-pmi-ioctl-pmi-get-configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--io-stack-location.md">IO_STACK_LOCATION</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs--irp.md">IRP</a>
</dt>
<dt>
<a href="..\pmi\ns-pmi--pmi-event.md">PMI_EVENT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20IOCTL_PMI_REGISTER_EVENT_NOTIFY control code%20 RELEASE:%20(11/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
