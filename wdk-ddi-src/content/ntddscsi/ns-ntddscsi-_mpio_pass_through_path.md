---
UID: NS:ntddscsi._MPIO_PASS_THROUGH_PATH
title: "_MPIO_PASS_THROUGH_PATH"
author: windows-driver-content
description: The MPIO_PASS_THROUGH_PATH structure is used together with an IOCTL_MPIO_PASS_THROUGH_PATH request to instruct the port driver to send an embedded SCSI command to the target device.
old-location: storage\mpio_pass_through_path.htm
old-project: storage
ms.assetid: 8c7f3832-3faa-4ece-8434-338f1b150ec1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PMPIO_PASS_THROUGH_PATH, MPIO_PASS_THROUGH_PATH, MPIO_PASS_THROUGH_PATH structure [Storage Devices], PMPIO_PASS_THROUGH_PATH, PMPIO_PASS_THROUGH_PATH structure pointer [Storage Devices], _MPIO_PASS_THROUGH_PATH, ntddscsi/MPIO_PASS_THROUGH_PATH, ntddscsi/PMPIO_PASS_THROUGH_PATH, storage.mpio_pass_through_path, structs-scsibus_0a643059-71aa-4dca-92a8-525924a999df.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	MPIO_PASS_THROUGH_PATH
product: Windows
targetos: Windows
req.typenames: MPIO_PASS_THROUGH_PATH, *PMPIO_PASS_THROUGH_PATH
---

# _MPIO_PASS_THROUGH_PATH structure
The <b>MPIO_PASS_THROUGH_PATH</b> structure is used together with an <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a> request to instruct the port driver to send an embedded SCSI command to the target device.

## Syntax
````
typedef struct _MPIO_PASS_THROUGH_PATH {
  SCSI_PASS_THROUGH PassThrough;
  ULONG             Version;
  USHORT            Length;
  UCHAR             Flags;
  UCHAR             PortNumber;
  ULONGLONG         MpioPathId;
} MPIO_PASS_THROUGH_PATH, *PMPIO_PASS_THROUGH_PATH;
````

## Members


`PassThrough`

Contains a <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> structure that is set up in the same way as it is for an <a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a> request.

`Version`

Should be zero.

`Length`

The size of the <b>MPIO_PASS_THROUGH_PATH</b> structure.

`Flags`

###### 



##########

`PortNumber`

The port number if MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set. Otherwise, this member is zero. If MPIO_IOCTL_FLAG_USE_SCSIADDRESS is set, the <b>PathId</b> and <b>TargetId</b> values are taken from the embedded <a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through.md">SCSI_PASS_THROUGH</a> structure.

`MpioPathId`

The <b>PathId</b> for the real LUN. This value can be obtained by using a WMI request for the PDO_INFORMATION that is associated with the real LUN. This value is set only if MPIO_IOCTL_FLAG_USE_PATHID is set.

## Remarks
The <b>MPIO_PASS_THROUGH_PATH</b> structure is used for a double-buffered device control request. To bypass buffering in system memory, callers should use <a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>. When the system handles an <b>IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</b> request, it locks down the buffer in user memory, and the device accesses this memory directly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddscsi.h (include Ntddscsi.h) |

## See Also

<a href="..\storport\ns-storport-_scsi_request_block.md">SCSI_REQUEST_BLOCK</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through.md">IOCTL_SCSI_PASS_THROUGH</a>



<a href="..\ntddscsi\ns-ntddscsi-_scsi_pass_through_direct.md">SCSI_PASS_THROUGH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path_direct.md">IOCTL_MPIO_PASS_THROUGH_PATH_DIRECT</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_mpio_pass_through_path.md">IOCTL_MPIO_PASS_THROUGH_PATH</a>



<a href="..\ntddscsi\ni-ntddscsi-ioctl_scsi_pass_through_direct.md">IOCTL_SCSI_PASS_THROUGH_DIRECT</a>