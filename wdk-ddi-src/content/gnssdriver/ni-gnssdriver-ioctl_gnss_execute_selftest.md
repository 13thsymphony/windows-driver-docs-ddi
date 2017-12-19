---
UID: NI.gnssdriver.IOCTL_GNSS_EXECUTE_SELFTEST
title: IOCTL_GNSS_EXECUTE_SELFTEST
author: windows-driver-content
description: The IOCTL_GNSS_EXECUTE_SELFTEST control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.
old-location: sensors\ioctl_gnss_execute_selftest.htm
old-project: sensors
ms.assetid: EAD10523-FFA0-4B08-BCBD-A20C90A1B8F6
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
req.alt-api: IOCTL_GNSS_EXECUTE_SELFTEST
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

# IOCTL_GNSS_EXECUTE_SELFTEST IOCTL



## -description
The <b>IOCTL_GNSS_EXECUTE_SELFTEST</b> control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.



## -ioctlparameters

### -input-buffer
A pointer to a <b>GNSS_SELFTESTCONFIG</b> structure.


### -input-buffer-length
Set to sizeof(GNSS_SELFTESTCONFIG).




### -output-buffer
A pointer to a <b>GNSS_SELFTESTRESULT</b> structure.




### -output-buffer-length
Set to sizeof(GNSS_SELFTESTRESULT).




### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code. 


## -remarks
The GNSS test application must wait for a status response from the test, and be resilient to the GNSS driver not responding.

The GNSS driver must fail a new self test session request if there is already a test in progress.

Once the GNSS driver accepts the self test session parameters, validates them and starts the test in the GNSS engine. The GNSS driver completes the I/O request after completing the tests and returning the status to the GNSS test application.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_EXECUTE_SELFTEST control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

