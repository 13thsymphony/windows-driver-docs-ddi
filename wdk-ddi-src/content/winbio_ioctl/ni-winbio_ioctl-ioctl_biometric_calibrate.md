---
UID : NI:winbio_ioctl.IOCTL_BIOMETRIC_CALIBRATE
title : IOCTL_BIOMETRIC_CALIBRATE
author : windows-driver-content
description : The IOCTL_BIOMETRIC_CALIBRATE IOCTL directs the driver to perform any necessary steps to calibrate the device for use.
old-location : biometric\ioctl_biometric_calibrate.htm
old-project : biometric
ms.assetid : 3ffd954f-91f8-4896-b105-86e07a5b6be7
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
req.alt-api : IOCTL_BIOMETRIC_CALIBRATE
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

# IOCTL_BIOMETRIC_CALIBRATE IOCTL
The IOCTL_BIOMETRIC_CALIBRATE IOCTL directs the driver to perform any necessary steps to calibrate the device for use.  Internally, the driver may also collect and return vendor specific calibration data to be analyzed by an application. Vendor-supplied WBDI drivers must support this IOCTL.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
None.

### Input Buffer Length
None.

### Output Buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_calibration_info.md">WINBIO_CALIBRATION_INFO</a> structure.

### Output Buffer Length
Length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_calibration_info.md">WINBIO_CALIBRATION_INFO</a> structure. 

The vendor-supplied driver can optionally return a DWORD-sized buffer that specifies the buffer size necessary for the requested operation.

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
        If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of WINBIO_CALIBRATION_INFO with the status of the Biometric operation.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | winbio_ioctl.h |
| **IRQL** |  |