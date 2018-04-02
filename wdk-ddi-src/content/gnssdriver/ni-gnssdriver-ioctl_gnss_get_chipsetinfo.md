---
UID: NI:gnssdriver.IOCTL_GNSS_GET_CHIPSETINFO
title: IOCTL_GNSS_GET_CHIPSETINFO
author: windows-driver-content
description: The IOCTL_GNSS_GET_CHIPSETINFO control code is used by the GNSS manufacturing test application to get information about the GNSS chipset.
old-location: sensors\ioctl_gnss_get_chipsetinfo.htm
old-project: sensors
ms.assetid: 9E57757B-65BA-40FF-98F9-F771C48EFF9E
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_GET_CHIPSETINFO, IOCTL_GNSS_GET_CHIPSETINFO control code [Sensor Devices], gnssdriver/IOCTL_GNSS_GET_CHIPSETINFO, sensors.ioctl_gnss_get_chipsetinfo
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
-	IOCTL_GNSS_GET_CHIPSETINFO
product:
- Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_GET_CHIPSETINFO IOCTL
The <b>IOCTL_GNSS_GET_CHIPSETINFO</b> 
   control code is used by the GNSS manufacturing test application to get information about the GNSS chipset. This information may be used by the test applications to decide which sets of tests should be executed, in which order, and map the response codes from the self tests into error conditions specific to the manufacturer or the chipset.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Set to NULL.

### Input Buffer Length
Set to 0.

### Output Buffer
A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn925098">GNSS_CHIPSETINFO</a> structure.

### Output Buffer Length
Set to sizeof(GNSS_CHIPSETINFO).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="GNSS_test_application_notes"></a><a id="gnss_test_application_notes"></a><a id="GNSS_TEST_APPLICATION_NOTES"></a>GNSS test application notes</h3>
The GNSS test application must wait for the response from the GNSS driver and be resilient to the GNSS driver not responding.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
The GNSS driver must respond with the information about the GNSS chipset.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>