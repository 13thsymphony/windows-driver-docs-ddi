---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_EX
title: "_SCSI_PASS_THROUGH_EX"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_ex.htm
old-project: storage
ms.assetid: 3D00B42C-7320-4044-BA7D-71A9BD05B30E
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_PASS_THROUGH_EX, PSCSI_PASS_THROUGH_EX, PSCSI_PASS_THROUGH_EX structure pointer [Storage Devices], SCSI_PASS_THROUGH_EX, SCSI_PASS_THROUGH_EX structure [Storage Devices], _SCSI_PASS_THROUGH_EX, ntddscsi/PSCSI_PASS_THROUGH_EX, ntddscsi/SCSI_PASS_THROUGH_EX, storage.scsi_pass_through_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	ntddscsi.h
api_name:
-	SCSI_PASS_THROUGH_EX
product: Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_EX, *PSCSI_PASS_THROUGH_EX
---

# _SCSI_PASS_THROUGH_EX structure
The <b>SCSI_PASS_THROUGH_EX</b> structure is used in conjunction with an <b>IOCTL_SCSI_PASS_THROUGH_EX</b> request to instruct the port driver to send an embedded SCSI command to the target device. <b>SCSI_PASS_THROUGH_EX</b> can contain a bi-directional data transfers and a variable length command data block.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSI_PASS_THROUGH_EX {
  USHORT    Version;
  USHORT    Length;
  ULONG     CdbLength;
  UCHAR     StorAddressLength;
  UCHAR     ScsiStatus;
  UCHAR     SenseInfoLength;
  UCHAR     DataDirection;
  UCHAR     Reserved;
  ULONG     TimeOutValue;
  ULONG     StorAddressOffset;
  ULONG     SenseInfoOffset;
  ULONG     DataOutTransferLength;
  ULONG     DataInTransferLength;
  ULONG_PTR DataOutBufferOffset;
  ULONG_PTR DataInBufferOffset;
  UCHAR     Cdb[ANYSIZE_ARRAY];
} SCSI_PASS_THROUGH_EX, *PSCSI_PASS_THROUGH_EX;
````

## Members


`Version`

The version of this structure. Set to 0.

`Length`

The size of the this structure. Set to <b>sizeof</b>(SCSI_PASS_THROUGH_EX).

`CdbLength`

Indicates the size in bytes of the SCSI command descriptor block in <b>Cdb</b>.

`StorAddressLength`

The length of the storage device address structure at the offset of <b>StorAddressOffset</b> after this structure.

`ScsiStatus`

Reports the SCSI status that was returned by the HBA or the target device.

`SenseInfoLength`

Indicates the size in bytes of the request-sense buffer. This member is optional and can be set to 0.

`DataDirection`

#####  This field must have one of these values:



########

`Reserved`

Reserved. Set to 0.

`TimeOutValue`

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.

`StorAddressOffset`

The location of the target storage device address structure, in bytes, from the beginning of this structure.

`SenseInfoOffset`

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.

`DataOutTransferLength`

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataOutTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.

`DataInTransferLength`

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataInTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.

`DataOutBufferOffset`

Contains an offset from the beginning of this structure to the output data buffer. The offset must respect the data alignment requirements of the device.

`DataInBufferOffset`

Contains an offset from the beginning of this structure to the input data buffer. The offset must respect the data alignment requirements of the device.

`Cdb`

Specifies the SCSI command descriptor block to be sent to the target device.

## Remarks
The <b>SCSI_PASS_THROUGH_EX</b> structure is used with the  <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a> control code, which is a buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. When handling an <b>IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</b> request, the system locks down the buffer in user memory and the device accesses this memory directly. 

<div class="alert"><b>Note</b>  Drivers executing on a 64 bit version of Windows must use the <b>SCSI_PASS_THROUGH32_EX</b> structure as the request data type  when handling an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a> request from a 32 bit process.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_ex.md">IOCTL_SCSI_PASS_THROUGH_EX</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>