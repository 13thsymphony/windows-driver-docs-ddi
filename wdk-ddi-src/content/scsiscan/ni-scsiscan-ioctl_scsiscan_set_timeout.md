---
UID: NI.scsiscan.IOCTL_SCSISCAN_SET_TIMEOUT
title: IOCTL_SCSISCAN_SET_TIMEOUT
author: windows-driver-content
description: The IOCTL_SCSISCAN_SET_TIMEOUT control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device.
old-location: image\ioctl_scsiscan_set_timeout.htm
old-project: image
ms.assetid: 987816b3-ea5f-4689-b81f-f6d3328516c4
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _ZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: scsiscan.h
req.include-header: Scsiscan.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SCSISCAN_SET_TIMEOUT
req.alt-loc: scsiscan.h
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
req.product: Windows 10 or later.
---

# IOCTL_SCSISCAN_SET_TIMEOUT IOCTL



## -description
The <b>IOCTL_SCSISCAN_SET_TIMEOUT</b> control code modifies the time-out value used by the kernel-mode still image driver for SCSI buses when it accesses a device.



## -syntax

````
ULONG timeout = 240;
fRet = DeviceIoControl( m_DeviceDataHandle,
        (DWORD)IOCTL_SCSISCAN_SET_TIMEOUT,
        &timeout,
        sizeof(ULONG),
        NULL, NULL, &dwBytesReturned, NULL);
````


## -ioctlparameters

### -input-buffer
The location containing a time-out value, in half seconds.


### -input-buffer-length
Size of the input buffer


### -output-buffer
Set to NULL.


### -output-buffer-length
Set to 0.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
When the kernel-mode SCSI still image driver sends a SCSI command to a device, by default the driver waits 30 seconds before timing out the operation. You can change the time-out value for a device by calling the <b>DeviceloControl</b> function with the <a href="..\scsiscan\ni-scsiscan-ioctl_scsiscan_cmd.md">IOCTL_SCSISCAN_CMD</a> control code. The specified time-out value stays in effect until the device is closed.

Time-out values are specified in half seconds. Thus a specified value of 100 causes the driver to wait 50 seconds before timing out the device.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

<b>Code example</b>


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Scsiscan.h (include Scsiscan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlotherssynchronously">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendinternalioctlsynchronously">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="wdf.wdfiotargetsendioctlsynchronously">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [image\image]:%20IOCTL_SCSISCAN_SET_TIMEOUT control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

