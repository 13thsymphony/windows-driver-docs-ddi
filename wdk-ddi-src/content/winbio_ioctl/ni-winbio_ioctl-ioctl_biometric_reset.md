---
UID: NI:winbio_ioctl.IOCTL_BIOMETRIC_RESET
title: IOCTL_BIOMETRIC_RESET
author: windows-driver-content
description: The IOCTL_BIOMETRIC_RESET IOCTL resets the device to a known or idle state, according to the current power state. Vendor-supplied WBDI drivers must support this IOCTL.
old-location: biometric\ioctl_biometric_reset.htm
old-project: biometric
ms.assetid: 4385911b-ae38-4748-ad11-cc161922776a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: biometric.ioctl_biometric_reset, IOCTL_BIOMETRIC_RESET control code [Biometric Devices], IOCTL_BIOMETRIC_RESET, winbio_ioctl/IOCTL_BIOMETRIC_RESET, biometric_ref_4043b840-5b38-40b2-bd80-282a28badd14.xml
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
-	IOCTL_BIOMETRIC_RESET
product: Windows
targetos: Windows
req.typenames: "*PBMP_IMAGE_INFO, BMP_IMAGE_INFO"
req.product: Windows 10 or later.
---

# IOCTL_BIOMETRIC_RESET IOCTL
The IOCTL_BIOMETRIC_RESET IOCTL resets the device to a known or idle state, according to the current power state.  Vendor-supplied WBDI drivers must support this IOCTL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_blank_payload.md">WINBIO_BLANK_PAYLOAD</a> structure.

### Output Buffer Length
The length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_blank_payload.md">WINBIO_BLANK_PAYLOAD</a> structure.

The vendor-supplied driver can optionally return a DWORD-sized buffer that specifies the buffer size necessary for the requested operation.

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
IOCTL_BIOMETRIC_RESET cancels a data collection IOCTL, if one is pending.  If there is a vendor-specific operation in progress, the driver should cancel the operation and reset the device whenever possible. 

If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of WINBIO_BLANK_PAYLOAD with the status of the Biometric operation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Header** | winbio_ioctl.h |