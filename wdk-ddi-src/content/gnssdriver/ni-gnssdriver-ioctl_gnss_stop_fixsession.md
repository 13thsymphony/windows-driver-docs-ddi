---
UID: NI:gnssdriver.IOCTL_GNSS_STOP_FIXSESSION
title: IOCTL_GNSS_STOP_FIXSESSION
author: windows-driver-content
description: The IOCTL_GNSS_STOP_FIXSESSION control code is used by the GNSS adapter to stop an active fix session.
old-location: sensors\ioctl_gnss_stop_fixsession.htm
old-project: sensors
ms.assetid: 3A15A61A-8822-4E20-9979-B89BFA092281
ms.author: windowsdriverdev
ms.date: 12/14/2017
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
req.alt-api: IOCTL_GNSS_STOP_FIXSESSION
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
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_STOP_FIXSESSION IOCTL



## -description
The <b>IOCTL_GNSS_STOP_FIXSESSION</b> control code is used by the GNSS adapter to stop an active fix session.



## -ioctlparameters

### -input-buffer
A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_stopfixsession_param.md">GNSS_STOPFIXSESSION_PARAM</a> structure.


### -input-buffer-length
Set to sizeof(GNSS_STOPFIXSESSION_PARAM).


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
The driver sets an NTSTATUS value to indicate one of the following results.

The fix session successfully stopped.

The fix session is already stopped or is not active.

The GNSS adapter always issues a stop fix for every successful start fix. If multi-session support is not present, the GNSS adapter stops any active fix session of the same type before issuing a new start fix request.

The GNSS driver must cancel/stop all pending fix requests and then complete the I/O so that when this call returns, the adapter does not receive any fix data pertaining to the stopped session.

If no other fix sessions are active, the GNSS driver should keep the GNSS engine in a cold state.


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
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>
</dt>
<dt>
<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_STOP_FIXSESSION control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

