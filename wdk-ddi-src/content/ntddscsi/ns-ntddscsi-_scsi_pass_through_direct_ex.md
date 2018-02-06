---
UID: NS:ntddscsi._SCSI_PASS_THROUGH_DIRECT_EX
title: "_SCSI_PASS_THROUGH_DIRECT_EX"
author: windows-driver-content
description: The SCSI_PASS_THROUGH_DIRECT_EX structure is used in conjunction with an IOCTL_SCSI_PASS_THROUGH_DIRECT_EX request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\scsi_pass_through_direct_ex.htm
old-project: storage
ms.assetid: FE699F78-99AC-46E0-9C51-6F69A5C4932C
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: SCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX structure [Storage Devices], storage.scsi_pass_through_direct_ex, PSCSI_PASS_THROUGH_DIRECT_EX structure pointer [Storage Devices], ntddscsi/SCSI_PASS_THROUGH_DIRECT_EX, *PSCSI_PASS_THROUGH_DIRECT_EX, _SCSI_PASS_THROUGH_DIRECT_EX, PSCSI_PASS_THROUGH_DIRECT_EX, ntddscsi/PSCSI_PASS_THROUGH_DIRECT_EX
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddscsi.h
apiname:
-	SCSI_PASS_THROUGH_DIRECT_EX
product: Windows
targetos: Windows
req.typenames: "*PSCSI_PASS_THROUGH_DIRECT_EX, SCSI_PASS_THROUGH_DIRECT_EX"
---

# _SCSI_PASS_THROUGH_DIRECT_EX structure
The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used in conjunction with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request to instruct the port driver to send an embedded SCSI command to the target device. <b>SCSI_PASS_THROUGH_DIRECT_EX</b> can contain a bi-directional data transfers and a variable length command data block.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _SCSI_PASS_THROUGH_DIRECT_EX {
  USHORT Version;
  USHORT Length;
  ULONG  CdbLength;
  UCHAR  StorAddressLength;
  UCHAR  ScsiStatus;
  UCHAR  SenseInfoLength;
  UCHAR  DataDirection;
  UCHAR  Reserved;
  ULONG  TimeOutValue;
  ULONG  StorAddressOffset;
  ULONG  SenseInfoOffset;
  ULONG  DataOutTransferLength;
  ULONG  DataInTransferLength;
  VOID   DataOutBuffer;
  VOID   DataInBuffer;
  UCHAR  Cdb[ANYSIZE_ARRAY];
} SCSI_PASS_THROUGH_DIRECT_EX, *PSCSI_PASS_THROUGH_DIRECT_EX;
````

## Members


`Cdb`

Specifies the SCSI command descriptor block to be sent to the target device.

`CdbLength`

Indicates the size in bytes of the SCSI command descriptor block in <b>Cdb</b>.

`DataDirection`

#### 



####  This field must have one of these values:

`DataInBuffer`

A pointer to a input data buffer.

`DataInTransferLength`

Indicates the size in bytes of the input data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataInTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no input data buffer is present, this member is set to 0.

`DataOutBuffer`

A pointer to a output data buffer.

`DataOutTransferLength`

Indicates the size in bytes of the output data buffer. Many devices transfer chunks of data of predefined length. The value in <b>DataOutTransferLength</b> must be an integral multiple of this predefined, minimum length that is specified by the device. If an underrun occurs, the miniport driver must update this member to the number of bytes actually transferred. If no output data buffer is present, this member is set to 0.

`Length`

The size of the this structure. Set to <b>sizeof</b>(SCSI_PASS_THROUGH_DIRECT_EX).

`Reserved`

Reserved. Set to 0.

`ScsiStatus`

Reports the SCSI status that was returned by the HBA or the target device.

`SenseInfoLength`

Indicates the size in bytes of the request-sense buffer. This member is optional and can be set to 0.

`SenseInfoOffset`

Offset from the beginning of this structure to the request-sense buffer. Set to 0 if no request-sense buffer is present.

`StorAddressLength`

The length of the storage device address structure at the offset of <b>StorAddressOffset</b> after this structure. This is set to <b>sizeof</b>(STOR_ADDR_BTL8).

`StorAddressOffset`

The location of the target device's <a href="..\storport\ns-storport-_stor_addr_btl8.md">STOR_ADDR_BTL8</a> address structure, in bytes, from the beginning of this structure.

`TimeOutValue`

Indicates the interval in seconds that the request can execute before the port driver considers it timed out.

`Version`

The version of this structure. Set to 0.

## Remarks
The <b>SCSI_PASS_THROUGH_DIRECT_EX</b> structure is used with <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>. With this request, the system locks down the buffer in user memory and the device accesses this memory directly. For a double-buffered equivalent of this device control request see <b>IOCTL_SCSI_PASS_THROUGH_EX</b> and <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_ex.md">SCSI_PASS_THROUGH_EX</a>.
<div class="alert"><b>Note</b>  Drivers executing on a 64 bit version of Windows must use the <b>SCSI_PASS_THROUGH_DIRECT32_EX</b> structure as the request data type  when handling an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a> request from a 32 bit process.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\storport\ns-storport-_stor_addr_btl8.md">STOR_ADDR_BTL8</a>

<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct_ex.md">IOCTL_SCSI_PASS_THROUGH_DIRECT_EX</a>

<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20SCSI_PASS_THROUGH_DIRECT_EX structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>