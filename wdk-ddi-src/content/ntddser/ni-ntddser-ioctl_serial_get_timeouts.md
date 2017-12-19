---
UID: NI.ntddser.IOCTL_SERIAL_GET_TIMEOUTS
title: IOCTL_SERIAL_GET_TIMEOUTS
author: windows-driver-content
description: The IOCTL_SERIAL_GET_TIMEOUTS request returns the current setting of the time-out value that the system-supplied bus driver for parallel ports uses with write requests.
old-location: parports\ioctl_serial_get_timeouts.htm
old-project: parports
ms.assetid: 8db92af3-d970-4740-8d49-46019b3ea016
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
req.alt-api: IOCTL_SERIAL_GET_TIMEOUTS
req.alt-loc: ntddser.h
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

# IOCTL_SERIAL_GET_TIMEOUTS IOCTL



## -description

The IOCTL_SERIAL_GET_TIMEOUTS request returns the current setting of the time-out value that the system-supplied bus driver for parallel ports uses with write requests. The parallel port bus driver does not queue a get time-outs request. The write time-out value is used with SPP and SW_ECP modes. 

A client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a> request to set time-out values.



The IOCTL_SERIAL_GET_TIMEOUTS request returns the current setting of the time-out value that the system-supplied bus driver for parallel ports uses with write requests. The parallel port bus driver does not queue a get time-outs request. The write time-out value is used with SPP and SW_ECP modes. 

A client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a> request to set time-out values.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> points to a SERIAL_TIMEOUTS structure that the client allocates to output time-out information. The parallel port bus driver sets the <b>WriteTotalTimeoutConstant</b> member to the time-out value in milliseconds.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a SERIAL_TIMEOUTS structure. 


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a SERIAL_TIMEOUTS structure. Otherwise, the <b>Information</b> member is set to zero. 

The <b>Status</b> member is set to one of the generic status values returned by device control requests for parallel devices or to  the following value:



The value of the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is less than the size, in bytes, of a SERIAL_TIMEOUTS structure.


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
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [parports\parports]:%20IOCTL_SERIAL_GET_TIMEOUTS control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

