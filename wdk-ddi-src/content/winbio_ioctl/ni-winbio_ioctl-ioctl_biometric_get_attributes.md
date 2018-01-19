---
UID : NI:winbio_ioctl.IOCTL_BIOMETRIC_GET_ATTRIBUTES
title : IOCTL_BIOMETRIC_GET_ATTRIBUTES
author : windows-driver-content
description : The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.
old-location : biometric\ioctl_biometric_get_attributes.htm
old-project : biometric
ms.assetid : 7a855435-017e-4724-adb4-976403015a93
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : IWiaTransferCallback, IWiaTransferCallback::TransferCallback, TransferCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : ioctl
req.header : winbio_ioctl.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IOCTL_BIOMETRIC_GET_ATTRIBUTES
req.alt-loc : Winbio_ioctl.h
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
req.typenames : BMP_IMAGE_INFO, *PBMP_IMAGE_INFO
req.product : Windows 10 or later.
---

# IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL
The IOCTL_BIOMETRIC_GET_ATTRIBUTES IOCTL returns a structure that contains a set of attributes for the sensor. Vendor-supplied WBDI drivers must support this IOCTL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_sensor_attributes.md">WINBIO_SENSOR_ATTRIBUTES</a> structure.

### Output Buffer Length
The smallest valid output buffer size is the size of DWORD.  If the driver receives an DWORD-sized output buffer, the driver should return the buffer size necessary for the requested operation.

### Input / Output Buffer
<text></text>

### Input / Output Buffer Length
<text></text>

### Status Block
I/O Status block
Indicates whether the DeviceIoControl call to the driver completed and the OUT payload is valid.

The <b>Status</b> member is set to one of the values in the following table.

S_OK, STATUS_SUCCESS

The operation completed successfully.  If the size of data returned is DWORD, the payload contains the size of the buffer necessary for the call.  Otherwise, the payload contains the full output buffer.

E_INVALIDARG

The parameters were not specified correctly.

E_UNKNOWN

Any other failure that prevents the payload from being filled in.

E_UNEXPECTED

Any other failure that prevents the payload from being filled in.

E_FAIL

Any other failure that prevents the payload from being filled in.

    ## Remarks
        If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_sensor_attributes.md">WINBIO_SENSOR_ATTRIBUTES</a> with an HRESULT value indicating the status of the biometric operation.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | winbio_ioctl.h |
| **IRQL** |  |