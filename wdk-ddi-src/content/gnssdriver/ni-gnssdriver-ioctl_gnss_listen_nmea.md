---
UID: NI.gnssdriver.IOCTL_GNSS_LISTEN_NMEA
title: IOCTL_GNSS_LISTEN_NMEA
author: windows-driver-content
description: The IOCTL_GNSS_LISTEN_NMEA control code is used to start listening for NMEA events from the driver.
old-location: sensors\ioctl_gnss_listen_nmea.htm
old-project: sensors
ms.assetid: 975F5FB4-503D-44E7-8D4C-2AEFE72B672B
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: GNSS_SUPL_CERT_ACTION, GNSS_SUPL_CERT_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_GNSS_LISTEN_NMEA
req.alt-loc: gnssdriver.h
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

# IOCTL_GNSS_LISTEN_NMEA IOCTL



## -description
The <b>IOCTL_GNSS_LISTEN_NMEA</b> control code is used to start listening for NMEA events from the driver.



## -ioctlparameters

### -input-buffer
Set to NULL.


### -input-buffer-length
Set to 0.




### -output-buffer
A pointer to a <a href="sensors.gnss_event">GNSS_EVENT</a> structure.




### -output-buffer-length
Set to sizeof(GNSS_EVENT).




### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
The <b>EventType</b> must be set to <b>GNSS_Event_NmeaData</b>.

The GNSS adapter does not use this IOCTL.

The driver can complete this call when it has NMEA data to send to the calling client. This calling client will typically be a test tool created by the OEM.

The calling client that wishes to receive NMEA data needs to do the following tasks:

Ensure that NMEA logging is active.

Ensures that this request is always pending, so that the driver can return NMEA data when available.

When the driver completes the I/O call, the calling client will need to issue another IOCTL to continue waiting for further NMEA data.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_LISTEN_NMEA control code%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

