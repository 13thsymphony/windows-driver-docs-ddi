---
UID: NI:gnssdriver.IOCTL_GNSS_GET_DEVICE_CAPABILITY
title: IOCTL_GNSS_GET_DEVICE_CAPABILITY
author: windows-driver-content
description: The IOCTL_GNSS_GET_DEVICE_CAPABILITY control code is used by the GNSS adapter to get the GNSS driver and device capabilities.
old-location: sensors\ioctl_gnss_get_device_capability.htm
old-project: sensors
ms.assetid: 28673D2A-5DD6-42CD-BD91-5C30B905ECF0
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_GNSS_GET_DEVICE_CAPABILITY, IOCTL_GNSS_GET_DEVICE_CAPABILITY control code [Sensor Devices], gnssdriver/IOCTL_GNSS_GET_DEVICE_CAPABILITY, sensors.ioctl_gnss_get_device_capability
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
-	IOCTL_GNSS_GET_DEVICE_CAPABILITY
product: Windows
targetos: Windows
req.typenames: GNSS_SUPL_CERT_ACTION
---

# IOCTL_GNSS_GET_DEVICE_CAPABILITY IOCTL
The IOCTL_GNSS_GET_DEVICE_CAPABILITY control code is used by the GNSS adapter to get the GNSS driver and device capabilities. The GNSS driver also specifies various support requirements from the HLOS components. This information is needed by the GNSS driver as well as the location service for deferring location-specific functionality to the GNSS device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
Set to NULL.

### Input Buffer Length
Set to 0.

### Output Buffer
Pointer to a GNSS_DEVICE_CAPABILITY structure.

### Output Buffer Length
Set to sizeof(GNSS_DEVICE_CAPABILITY).

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="GNSS_adapter_notes"></a><a id="gnss_adapter_notes"></a><a id="GNSS_ADAPTER_NOTES"></a>GNSS adapter notes</h3>
On completion, the GNSS adapter stores the capability information in its state variables and communicates the same to other location components. Depending on the specific device capabilities and/or support requirements, the GNSS adapter can also load/unload other components to provide the needed support.

<h3><a id="GNSS_driver_notes"></a><a id="gnss_driver_notes"></a><a id="GNSS_DRIVER_NOTES"></a>GNSS driver notes</h3>
Driver fills the output buffer and completes the I/O.

This should be called when the GNSS adapter is initializing the GNSS driver.

Even if the driver supports a specific functionality or needs a specific functionality support from the HLOS, it is not guaranteed that the HLOS will leverage a specific driver capability, or will provided the needed level of support to the driver.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542894">Creating IOCTL Requests in Drivers</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548651">WdfIoTargetSendInternalIoctlOthersSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548656">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548660">WdfIoTargetSendIoctlSynchronously</a>