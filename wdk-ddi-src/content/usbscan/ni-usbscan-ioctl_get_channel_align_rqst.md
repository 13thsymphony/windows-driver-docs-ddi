---
UID: NI:usbscan.IOCTL_GET_CHANNEL_ALIGN_RQST
title: IOCTL_GET_CHANNEL_ALIGN_RQST
author: windows-driver-content
description: Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle.
old-location: image\ioctl_get_channel_align_rqst.htm
old-project: image
ms.assetid: 8025a092-470a-4cd5-af63-21f82e094933
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: IOCTL_GET_CHANNEL_ALIGN_RQST, IOCTL_GET_CHANNEL_ALIGN_RQST control code [Imaging Devices], image.ioctl_get_channel_align_rqst, stifnc_a81e47eb-3d6f-4bfb-a371-08c42602bc5a.xml, usbscan/IOCTL_GET_CHANNEL_ALIGN_RQST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbscan.h
req.include-header: Usbscan.h
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
-	Usbscan.h
api_name:
-	IOCTL_GET_CHANNEL_ALIGN_RQST
product:
- Windows
targetos: Windows
req.typenames: RAW_PIPE_TYPE
req.product: Windows 10 or later.
---

# IOCTL_GET_CHANNEL_ALIGN_RQST IOCTL
Returns a USB device's maximum packet size for the read, write, and interrupt transfer pipes associated with the specified device handle.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<b>NULL</b>.

### Input Buffer Length
Zero.

### Output Buffer
Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539466">CHANNEL_INFO</a> structure.

### Output Buffer Length
Size of the output buffer.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
<b>Irp-&gt;IoStatus.Status</b> is set to STATUS_SUCCESS if the request is successful. Otherwise, <b>Status</b> to the appropriate error condition as a <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NTSTATUS</a> code.

## Remarks
<h3><a id="ddk_ioctl_get_channel_align_rqst_si"></a><a id="DDK_IOCTL_GET_CHANNEL_ALIGN_RQST_SI"></a>DeviceIoControl Parameters</h3>


When the <b>DeviceloControl</b> function is called with the IOCTL_GET_CHANNEL_ALIGN_RQST I/O control code, the caller must specify the address of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539466">CHANNEL_INFO</a> structure as the function's <i>lpOutBuffer</i> parameter. The kernel-mode driver fills in the structure.

For more information, see <a href="https://msdn.microsoft.com/f9216d3c-4930-4c26-8eac-6ee500b038e0">Accessing Kernel-Mode Drivers for Still Image Devices</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | usbscan.h (include Usbscan.h) |