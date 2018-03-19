---
UID: NI:hidport.IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
title: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
author: windows-driver-content
description: The IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code obtains the physical descriptor of a HIDClass device.
old-location: hid\ioctl_umdf_get_physical_descriptor.htm
old-project: hid
ms.assetid: F5852D3B-FD30-4308-A08E-B7DEA86A35E6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR control code, hid.ioctl_umdf_get_physical_descriptor, hidport/IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR, umdf.ioctl_umdf_get_physical_descriptor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: hidport.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
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
-	Hidport.h
api_name:
-	IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: USAGE_AND_PAGE, *PUSAGE_AND_PAGE
---

# IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR IOCTL
The <b>IOCTL_UMDF_GET_PHYSICAL_DESCRIPTOR</b> 
   control code obtains the physical descriptor of a HIDClass device.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
A UMDF-based driver obtains the size, in bytes, of the buffer by calling <a href="https://msdn.microsoft.com/96de6f7a-da1d-44a6-b1f7-44859312a662">IWDFRequest::GetDeviceIoControlParameters</a> and providing the  <i>pOutBufferSize</i> parameter.

### Input Buffer Length
<text></text>

### Output Buffer
The driver copies the physical descriptor to the user buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.

### Output Buffer Length
The size of the buffer that is retrieved by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff559112">IWDFIoRequest::GetOutputMemory</a>.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
HID minidrivers that carry out the I/O to the device must also:

<ul>
<li>Call <a href="https://msdn.microsoft.com/dc2c907c-1e3b-418c-85f8-9902dc83f7ab">IWDFRequest::SetInformation</a> to set the number of bytes transferred from the device.</li>
<li>Call <a href="https://msdn.microsoft.com/2fa389f8-8277-4795-a89e-ac5d92004310">IWDFRequest::Complete</a> with S_OK to complete the request without error. Otherwise, set the appropriate HRESULT error code.</li>
</ul>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidport.h |

## See Also

<a href="..\hidclass\ni-hidclass-ioctl_get_physical_descriptor.md">IOCTL_GET_PHYSICAL_DESCRIPTOR</a>