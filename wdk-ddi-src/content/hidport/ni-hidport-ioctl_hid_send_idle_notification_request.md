---
UID: NI.hidport.IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
title: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
author: windows-driver-content
description: The IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.
old-location: hid\ioctl_hid_send_idle_notification_request.htm
old-project: hid
ms.assetid: AD653C7C-7C43-4258-98F8-3D9EDB51AE44
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: HidRegisterMinidriver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: Hidport.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST
req.alt-loc: Hidport.h
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

# IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST IOCTL



## -description
The <b>IOCTL_HID_SEND_IDLE_NOTIFICATION_REQUEST</b> 
   control code is the IOCTL of the idle notification request IRP that HIDClass sends to HID mini drivers, such as HIDUSB, to inform the bus driver that the device is now idle.

For general information about HIDClass devices, see <a href="https://msdn.microsoft.com/2d3efb38-4eba-43db-8cff-9fac30209952">HID Collections</a>. 



## -ioctlparameters

### -input-buffer
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, Status to the appropriate error condition as a <a href="kernel.ntstatus_value">NTSTATUS</a> code.


### -input-buffer-length
 The size of a status code.


### -output-buffer

       None.


### -output-buffer-length
None.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
The bus or port driver sets Irp-&gt;IoStatus.Status to STATUS_SUCCESS or the appropriate error status.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Hidport.h (include Hidport.h)</dt>
</dl>
</td>
</tr>
</table>