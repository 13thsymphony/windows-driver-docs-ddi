---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT_EX
title: "_SCSI_PASS_THROUGH_DIRECT_EX"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_DIRECT_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct_ex.htm
old-project: storage
ms.assetid: FE699F78-99AC-46E0-9C51-6F69A5C4932C
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX structure pointer [Storage Devices], SCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX structure [Storage Devices], _SCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/PSCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/SCSI_PASS_THROUGH_DIRECT_EX, storage.scsi_pass_through_direct_ex"
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
-	SCSI_PASS_THROUGH_DIRECT_EX
product: Windows
targetos: Windows
req.typenames: SCSI_PASS_THROUGH_DIRECT_EX, *PSCSI_PASS_THROUGH_DIRECT_EX
---

# _SCSI_PASS_THROUGH_DIRECT_EX structure
The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used in conjunction with an <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device. <b>SCSI_PASS_THROUGH_DIRECT_EX</b> can contain a bi-directional data transfers and a variable length command data block.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
```
typedef struct _SCSI_PASS_THROUGH_DIRECT_EX {
  ULONG Version;
  ULONG Length;
  ULONG CdbLength;
  ULONG StorAddressLength;
  UCHAR ScsiStatus;
  UCHAR SenseInfoLength;
  UCHAR DataDirection;
  UCHAR Reserved;
  ULONG TimeOutValue;
  ULONG StorAddressOffset;
  ULONG SenseInfoOffset;
  ULONG DataOutTransferLength;
  ULONG DataInTransferLength;
  VOID  *DataOutBuffer;
  VOID  *DataInBuffer;
  UCHAR Cdb[ANYSIZE_ARRAY];
} *PSCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX;
```

## Members


`Version`

The version of this structure. Set to 0.

`Length`

The size of the this structure. Set to <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT_EX).

`CdbLength`

Indicates the size in bytes of the SCSI command descriptor block in <b>Cdb</b>.

`StorAddressLength`

The length of the storage device address structure at the offset of <b>StorAddressOffset</b> after this structure. This is set to <b>sizeof</b>(STOR_ADDR_BTL8).

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

The location of the target device's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451521">STOR_ADDR_BTL8</a> address structure, in bytes, from the beginning of this structure.

`SenseInfoOffset`

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.

`DataOutTransferLength`

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataOutTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.

`DataInTransferLength`

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataInTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.

`DataOutBuffer`

A pointer to a output data buffer.

`DataInBuffer`

A pointer to a input data buffer.

`Cdb`

Specifies the SCSI command descriptor block to be sent to the target device.

## Remarks
The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used with <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see <b>IOCTL_SCSI_PASS_THROUGH_EX</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/jj553715">SCSI_PASS_THROUGH_EX</a>.

<div class="alert"><b>Note</b>  Drivers executing on a 64 bit version of Windows must use the <b>SCSI_PASS_THROUGH_DIRECT32_EX</b> structure as the request data type  when handling an <a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request from a 32 bit process.</div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff560521">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj602800">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565346">SCSI_PASS_THROUGH_DIRECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451521">STOR_ADDR_BTL8</a>