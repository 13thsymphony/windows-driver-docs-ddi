---
UID: NI.ntddser.IOCTL_SERIAL_WAIT_ON_MASK
title: IOCTL_SERIAL_WAIT_ON_MASK
author: windows-driver-content
description: The IOCTL_SERIAL_WAIT_ON_MASK request is used to wait for the occurrence of any wait event specified by using an IOCTL_SERIAL_SET_WAIT_MASK request.
old-location: serports\ioctl_serial_wait_on_mask.htm
old-project: serports
ms.assetid: b813bd59-249d-4cd1-bf56-4525c7f1fa1d
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_WAIT_ON_MASK
req.alt-loc: Ntddser.h
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

# IOCTL_SERIAL_WAIT_ON_MASK IOCTL



## -description
The <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is used to wait for the occurrence of any wait event specified by using an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request.

A wait-on-mask request is completed after one of the following events occurs:

A wait event occurs that was specified by the most recent set-wait-mask request.

An <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request is received while a wait-on-mask request is pending. The driver completes the pending wait-on-mask request with a status of STATUS_SUCCESS and the output wait mask is set to zero.

A client can wait for the wait events represented by flag bits <b>SERIAL_EV_RXCHAR</b> through <b>SERIAL_EV_EVENT2</b>. For more information about these event flags, see <a href="serports.serial_ev_xxx">SERIAL_EV_XXX</a>.

A client sends an <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to wait for the occurrence of an event that was specified in the wait mask supplied by the most recent <b>IOCTL_SERIAL_SET_WAIT_MASK</b> request. If one or more events in the current wait mask occur before the <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is sent, this request is immediately completed with a status of STATUS_SUCCESS and an output mask value that identifies the events. If no event in the wait mask occurs before the <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is sent, this request is marked as pending, and it waits in the serial controller queue for the next occurrence of an event in the current wait mask.

After a client's <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request is completed with a status of STATUS_SUCCESS and a nonzero output mask value, the client can send a new <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to wait for another event in the current wait mask. Only a new event that occurs after the previous <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request was completed will cause the new <b>IOCTL_SERIAL_WAIT_ON_MASK</b> request to be completed with a status of STATUS_SUCCESS and a nonzero output mask value.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
<b>AssociatedIrp.System</b> buffer points to a ULONG buffer that holds an event wait mask. The event wait mask indicates which wait events occurred. The event wait mask is set to zero or to the bitwise-OR of one or more of the <a href="serports.serial_ev_xxx">SERIAL_EV_XXX</a> flag bits.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The <b>Information</b> member is set to the size, in bytes, of a ULONG.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>. A status of STATUS_INVALID_PARAMETER indicates that no wait events are set, or a wait-on-mask request is already pending.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddser.h (include Ntddser.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>
</dt>
<dt>
<a href="serports.serial_ev_xxx">SERIAL_EV_XXX</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_WAIT_ON_MASK control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

