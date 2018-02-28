---
UID: NI:pmi.IOCTL_PMI_GET_MEASUREMENT
title: IOCTL_PMI_GET_MEASUREMENT
author: windows-driver-content
description: The IOCTL_PMI_GET_MEASUREMENT request returns the current measurement data from a power meter.
old-location: powermeter\ioctl_pmi_get_measurement.htm
old-project: powermeter
ms.assetid: 2f479147-cccb-44c8-bc86-37c6731cb95b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_PMI_GET_MEASUREMENT, IOCTL_PMI_GET_MEASUREMENT control code [Power Metering and Budgeting Devices], PowerMeterRef_2317a4b3-7909-4c52-a012-39c892a39154.xml, pmi/IOCTL_PMI_GET_MEASUREMENT, powermeter.ioctl_pmi_get_measurement
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: pmi.h
req.include-header: Pmi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems.
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
-	Pmi.h
api_name:
-	IOCTL_PMI_GET_MEASUREMENT
product: Windows
targetos: Windows
req.typenames: PMI_MEASUREMENT_UNIT
---

# IOCTL_PMI_GET_MEASUREMENT IOCTL
The <b>IOCTL_PMI_GET_MEASUREMENT</b> request returns the current measurement data from a power meter.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
The initiator-allocated output buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member of the IRP.

### Input Buffer Length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member of the IRP's current I/O stack location (<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>) is set to the size in bytes of the initiator-allocated output buffer that is pointed to by the <b>AssociatedIrp.SystemBuffer</b> member of the IRP. This size must be greater than or equal to <b>sizeof</b>(<a href="..\pmi\ns-pmi-_pmi_measurement_data.md">PMI_MEASUREMENT_DATA</a>) or the request fails with an error status of STATUS_BUFFER_TOO_SMALL.

### Output Buffer
If the request completes successfully, the output buffer pointed to by the <b>AssociatedIrp.SystemBuffer</b> member contains a <a href="..\pmi\ns-pmi-_pmi_measurement_data.md">PMI_MEASUREMENT_DATA</a> structure. This structure contains the requested measurement data.

### Output Buffer Length
The size of a <a href="..\pmi\ns-pmi-_pmi_measurement_data.md">PMI_MEASUREMENT_DATA</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
The <b>Information</b> member is set to the size, in bytes, of a <a href="..\pmi\ns-pmi-_pmi_measurement_data.md">PMI_MEASUREMENT_DATA</a> structure.

The <b>Status</b> member is set to one of the following values:

## Remarks
The <b>IOCTL_PMI_GET_MEASUREMENT</b> request queries the current measurement data from the power meter. This measurement data is sampled and averaged based on the power meter's measurement configuration parameters. The measurement configuration parameters are queried through the <a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a> request with an input <a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a> value of <b>PmiMeasurementConfiguration</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems. Available in Windows 7, Windows Server 2008 R2, and later versions of the Windows operating systems. |
| **Header** | pmi.h (include Pmi.h) |

## See Also

<a href="..\pmi\ni-pmi-ioctl_pmi_get_capabilities.md">IOCTL_PMI_GET_CAPABILITIES</a>



<a href="..\pmi\ni-pmi-ioctl_pmi_get_configuration.md">IOCTL_PMI_GET_CONFIGURATION</a>



<a href="..\wdm\ns-wdm-_irp.md">IRP</a>



<a href="..\pmi\ns-pmi-_pmi_measurement_data.md">PMI_MEASUREMENT_DATA</a>



<a href="..\wdm\ns-wdm-_io_stack_location.md">IO_STACK_LOCATION</a>



<a href="..\pmi\ne-pmi-pmi_configuration_type.md">PMI_CONFIGURATION_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [powermeter\powermeter]:%20IOCTL_PMI_GET_MEASUREMENT control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>