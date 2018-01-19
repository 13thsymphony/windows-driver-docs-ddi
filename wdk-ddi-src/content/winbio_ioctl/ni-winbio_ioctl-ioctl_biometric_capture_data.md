---
UID : NI:winbio_ioctl.IOCTL_BIOMETRIC_CAPTURE_DATA
title : IOCTL_BIOMETRIC_CAPTURE_DATA
author : windows-driver-content
description : The IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL directs the driver to retrieve the next scan of biometric data. This call should put the device into capture mode.Vendor-supplied WBDI drivers must support IOCTL_BIOMETRIC_CAPTURE_DATA.
old-location : biometric\ioctl_biometric_capture_data.htm
old-project : biometric
ms.assetid : 52c7007f-6038-41d8-b459-f0fa1b90fd5e
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
req.alt-api : IOCTL_BIOMETRIC_CAPTURE_DATA
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

# IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL
The IOCTL_BIOMETRIC_CAPTURE_DATA IOCTL directs the driver to retrieve the next scan of biometric data.   This call should put the device into capture mode.Vendor-supplied WBDI drivers must support IOCTL_BIOMETRIC_CAPTURE_DATA.



Vendor-supplied WBDI drivers must support IOCTL_BIOMETRIC_CAPTURE_DATA.

### Major Code
[IRP_MJ_DEVICE_CONTROL](xref:"https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control")

### Input Buffer
<a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_parameters.md">WINBIO_CAPTURE_PARAMETERS</a>

### Input Buffer Length
The length of a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_parameters.md">WINBIO_CAPTURE_PARAMETERS</a>
       structure.

### Output Buffer
The <b>AssociatedIrp</b>.<b>SystemBuffer</b> member points to a buffer that contains a <a href="..\winbio_ioctl\ns-winbio_ioctl-_winbio_capture_data.md">WINBIO_CAPTURE_DATA</a> structure.

The vendor-specific data in the WINBIO_BIR structure can be in any format the vendor would like to collect from the driver.  Vendors can choose to process data in the WBDI driver or in the engine adapter, but the data must be passed in one structure.

### Output Buffer Length
The smallest valid output buffer size is the size of DWORD.

If the driver receives a DWORD-sized output buffer, the driver must immediately return the buffer size necessary to complete the operation.  Do not wait for the swipe to occur to send the required buffer size.

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

WINBIO_E_DATA_COLLECTION_IN_PROGRESS

Device has an IOCTL_BIOMETRIC_CAPTURE_DATA pending.

E_UNKNOWN

Any other failure that prevents the payload from being filled in.

E_UNEXPECTED

Any other failure that prevents the payload from being filled in.

E_FAIL

Any other failure that prevents the payload from being filled in.

    ## Remarks
        Only one data collection IOCTL can be pending at any time.  If the device has an IOCTL_BIOMETRIC_CAPTURE_DATA pending, IOCTL_BIOMETRIC_CAPTURE_DATA must return WINBIO_E_DATA_COLLECTION_IN_PROGRESS.

IOCTL_BIOMETRIC_CAPTURE_DATA is a blocking data collection IOCTL that is completed when the biometric data capture occurs. 

If the vendor-supplied driver passes back the entire payload, it should fill in the <b>WinBioHresult</b> member of WINBIO_CAPTURE_DATA with the status of the Biometric operation.

Possible values include:



The operation completed successfully.

There is already a data collection IOCTL pending.

The format specified is not supported by this driver and device.

The type of data requested is not supported by this driver and device.

The device could not be put into biometric capture mode.  This could be because the device is in another non-data collection mode.

The operation was not completed due to device error.

The device is in the middle of a vendor-specific operation.

The operation was canceled either by the caller, or by someone issuing an IOCTL_BIOMETRIC_RESET

The capture purpose specified is not supported by the driver.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Header** | winbio_ioctl.h |
| **IRQL** |  |