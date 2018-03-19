---
UID: NI:bthioctl.IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
title: IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
author: windows-driver-content
description: The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that caused the Plug and Play (PnP) manager to load the current instance of the profile driver.
old-location: bltooth\ioctl_internal_bthenum_get_devinfo.htm
old-project: bltooth
ms.assetid: c0134541-2e17-41e5-b30a-493b1bb42d07
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_BTHENUM_GET_DEVINFO, IOCTL_INTERNAL_BTHENUM_GET_DEVINFO control code [Bluetooth Devices], bltooth.ioctl_internal_bthenum_get_devinfo, bth_ioctls_08047b17-31ae-4497-b83d-21e42058765f.xml, bthioctl/IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: bthioctl.h
req.include-header: Bthioctl.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: "<= PASSIVE_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthioctl.h
api_name:
-	IOCTL_INTERNAL_BTHENUM_GET_DEVINFO
product: Windows
targetos: Windows
req.typenames: HFP_BYPASS_CODEC_ID_V1, *PHFP_BYPASS_CODEC_ID_V1
---

# IOCTL_INTERNAL_BTHENUM_GET_DEVINFO IOCTL
The IOCTL_INTERNAL_BTHENUM_GET_DEVINFO request returns information about the remote device that
     caused the Plug and Play (PnP) manager to load the current instance of the profile driver.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The 
      <b>AssociatedIrp.SystemBuffer</b> member points to a buffer that holds a 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure that
      contains information about the device's state, the device's address, and class of device (CoD).

### Output Buffer Length
The length of a 
      <a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a> structure.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
If the request is successful, the 
      <b>Information</b> member of the STATUS_BLOCK structure is set to the size, in bytes, of the output
      buffer. Otherwise, the 
      <b>Information</b> member is set to zero.

The 
      <b>Status</b> member is set to one of the values in the following table.

<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
STATUS_SUCCESS

</td>
<td>
The IOCTL completed successfully.

</td>
</tr>
<tr>
<td>
STATUS_INVALID_BUFFER_SIZE

</td>
<td>
The output buffer was sized incorrectly.

</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthioctl.h (include Bthioctl.h) |
| **IRQL** | "<= PASSIVE_LEVEL" |

## See Also

<a href="http://go.microsoft.com/fwlink/p/?linkid=50713">BTH_DEVICE_INFO</a>