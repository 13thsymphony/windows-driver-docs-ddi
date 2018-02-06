---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_SET_INDICATOR
title: IOCTL_BIOMETRIC_SET_INDICATOR
author: windows-driver-content
description: The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.
old-location: biometric\ioctl_biometric_set_indicator.htm
old-project: biometric
ms.assetid: 5aaaf178-a137-4a98-a77f-b426514a8cd9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: biometric.ioctl_biometric_set_indicator, IOCTL_BIOMETRIC_SET_INDICATOR control code [Biometric Devices], IOCTL_BIOMETRIC_SET_INDICATOR, winbio_ioctl/IOCTL_BIOMETRIC_SET_INDICATOR, biometric_ref_46e6f908-83fd-4e5b-9cc4-183da4f178d2.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winbio_ioctl.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winbio_ioctl.h
apiname:
-	IOCTL_BIOMETRIC_SET_INDICATOR
product: Windows
targetos: Windows
req.typenames: "*PBMP_IMAGE_INFO, BMP_IMAGE_INFO"
req.product: Windows 10 or later.
---

# IOCTL_BIOMETRIC_SET_INDICATOR IOCTL
The IOCTL_BIOMETRIC_SET_INDICATOR IOCTL directs the driver to update the status of the indicator light.  The light can be turned on or off.  This IOCTL is optional.This IOCTL must be implemented if the driver supports the WINBIO_CAPABILITY_INDICATOR capability.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_set_indicator.md">WINBIO_SET_INDICATOR</a>

### Input Buffer Length
Length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_set_indicator.md">WINBIO_SET_INDICATOR</a> structure.

### Output Buffer
The AssociatedIrp.SystemBuffer member points to a buffer that contains a WINBIO_BLANK_PAYLOAD structure.

### Output Buffer Length
The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.
<table>
<tr>
<th>Status value</th>
<th>Description</th>
</tr>
<tr>
<td>
S_OK, STATUS_SUCCESS

</td>
<td>
The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.

</td>
</tr>
<tr>
<td>
E_INVALIDARG

</td>
<td>
The parameters were not specified correctly.

</td>
</tr>
<tr>
<td>
E_UNKNOWN

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
<tr>
<td>
E_UNEXPECTED

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
<tr>
<td>
E_FAIL

</td>
<td>
Any other failure that prevents the payload from being filled in.

</td>
</tr>
</table>

## Remarks
If the vendor-supplied driver passes back the entire payload, it should fill in the WinBioHresult member of WINBIO_BLANK_PAYLOAD with the status of the biometric operation.

Possible values include:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | winbio_ioctl.h |