---
UID : NI:gnssdriver.IOCTL_GNSS_EXECUTE_SELFTEST
title : IOCTL_GNSS_EXECUTE_SELFTEST
author : windows-driver-content
description : The IOCTL_GNSS_EXECUTE_SELFTEST control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.
old-location : sensors\ioctl_gnss_execute_selftest.htm
old-project : sensors
ms.assetid : EAD10523-FFA0-4B08-BCBD-A20C90A1B8F6
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : sensors.ioctl_gnss_execute_selftest, IOCTL_GNSS_EXECUTE_SELFTEST control code [Sensor Devices], IOCTL_GNSS_EXECUTE_SELFTEST, gnssdriver/IOCTL_GNSS_EXECUTE_SELFTEST
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : gnssdriver.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_EXECUTE_SELFTEST IOCTL
The <b>IOCTL_GNSS_EXECUTE_SELFTEST</b> control code is used by the GNSS manufacturing test application to initiate a self test in the GNSS lower stack.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A pointer to a <b>GNSS_SELFTESTCONFIG</b> structure.

### Input Buffer Length
Set to sizeof(GNSS_SELFTESTCONFIG).

### Output Buffer
A pointer to a <b>GNSS_SELFTESTRESULT</b> structure.

### Output Buffer Length
Set to sizeof(GNSS_SELFTESTRESULT).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>The GNSS test application must wait for a status response from the test, and be resilient to the GNSS driver not responding.
<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>The GNSS driver must fail a new self test session request if there is already a test in progress.

Once the GNSS driver accepts the self test session parameters, validates them and starts the test in the GNSS engine. The GNSS driver completes the I/O request after completing the tests and returning the status to the GNSS test application.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | gnssdriver.h |
| **IRQL** |  |

## See Also

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlotherssynchronously.md">WdfIoTargetSendInternalIoctlOthersSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [sensors\sensors]:%20IOCTL_GNSS_EXECUTE_SELFTEST control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>