---
UID: NI:gnssdriver.IOCTL_GNSS_INJECT_AGNSS
title: IOCTL_GNSS_INJECT_AGNSS
author: windows-driver-content
description: The IOCTL_GNSS_INJECT_AGNSS control code is used by the GNSS adapter to inject AGNSS data into the driver. This IOCTL is sent as a result of the driver previously responding to a pending IOCTL_GNSS_LISTEN_AGNSS request.
old-location: sensors\ioctl_gnss_inject_agnss.htm
old-project: sensors
ms.assetid: 68EC4397-1983-4D02-BF6E-599DC987E7E9
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_INJECT_AGNSS, IOCTL_GNSS_INJECT_AGNSS control code [Sensor Devices], gnssdriver/IOCTL_GNSS_INJECT_AGNSS, sensors.ioctl_gnss_inject_agnss
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	IOCTL_GNSS_INJECT_AGNSS
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_INJECT_AGNSS IOCTL
The <b>IOCTL_GNSS_INJECT_AGNSS</b> control code is used by the GNSS adapter to inject AGNSS data into the driver. This IOCTL is sent as a result of the driver previously responding to a pending <a href="..\gnssdriver\ni-gnssdriver-ioctl_gnss_listen_agnss.md">IOCTL_GNSS_LISTEN_AGNSS</a> request.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <a href="..\gnssdriver\ns-gnssdriver-gnss_agnss_inject.md">GNSS_AGNSS_INJECT</a> structure.

### Input Buffer Length
Set to sizeof(GNSS_AGNSS_INJECT).

### Output Buffer
Set to <b>NULL</b>.

### Output Buffer Length
Set to 0.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="Input"></a><a id="input"></a><a id="INPUT"></a>Input</h3>

<a href="..\gnssdriver\ns-gnssdriver-gnss_agnss_inject.md">GNSS_AGNSS_INJECT</a>


Depending on the InjectionType element, the appropriate data element is filled.

<h3><a id="Output"></a><a id="output"></a><a id="OUTPUT"></a>Output</h3>
NTSTATUS with the following indications:

<ul>
<li>
Success: AGNSS data injection was accepted.

</li>
<li>
Failed: AGNSS data injection failed.

</li>
</ul>
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
When the GNSS adapter fails to get time for injection, it sets the InjectionStatus element. The driver must check that this element indicates success, before actually using the element data.

In case of failure in gathering injection data, the adapter does not automatically retry. It is up to the driver to retry the same request sequent.

This is a fire-and-forget IOCTL. The GNSS adapter does not handle error even if the driver returns a failure indicating that the injection data was not used.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver completes the I/O request after consuming the injection data.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_INJECT_AGNSS control code%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>