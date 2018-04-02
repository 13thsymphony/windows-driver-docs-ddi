---
UID: NS:ntddcdrm._CDROM_WRITE_SPEED_DESCRIPTOR
title: "_CDROM_WRITE_SPEED_DESCRIPTOR"
author: windows-driver-content
description: The CDROM_WRITE_SPEED_DESCRIPTOR structure is returned for the IOCTL_CDROM_GET_PERFORMANCE IOCTL when the request type is CdromWriteSpeedRequest.
old-location: storage\cdrom_write_speed_descriptor.htm
old-project: storage
ms.assetid: 21CFAA26-3E11-4E3B-949A-C905813E56A8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PCDROM_WRITE_SPEED_DESCRIPTOR, CDROM_WRITE_SPEED_DESCRIPTOR, CDROM_WRITE_SPEED_DESCRIPTOR structure [Storage Devices], PCDROM_WRITE_SPEED_DESCRIPTOR, PCDROM_WRITE_SPEED_DESCRIPTOR structure pointer [Storage Devices], _CDROM_WRITE_SPEED_DESCRIPTOR, ntddcdrm/CDROM_WRITE_SPEED_DESCRIPTOR, ntddcdrm/PCDROM_WRITE_SPEED_DESCRIPTOR, storage.cdrom_write_speed_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
req.include-header: Ntddcdrm.h
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
-	Ntddcdrm.h
api_name:
-	CDROM_WRITE_SPEED_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: CDROM_WRITE_SPEED_DESCRIPTOR, *PCDROM_WRITE_SPEED_DESCRIPTOR
---

# _CDROM_WRITE_SPEED_DESCRIPTOR structure
The <b>CDROM_WRITE_SPEED_DESCRIPTOR</b> structure is returned for the <a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a> IOCTL when the request type is <b>CdromWriteSpeedRequest</b>. The IOCTL returns the  <a href="https://msdn.microsoft.com/library/windows/hardware/gg441232">CDROM_PERFORMANCE_HEADER</a> followed by one or more descriptors of type <b>CDROM_WRITE_SPEED_DESCRIPTOR</b>.

## Syntax
```
typedef struct _CDROM_WRITE_SPEED_DESCRIPTOR {
  UCHAR  : 1 MixedReadWrite;
  UCHAR  : 1 Exact;
  UCHAR  : 1 Reserved1;
  UCHAR  : 2 WriteRotationControl;
  UCHAR  : 3 Reserved2;
  UCHAR      Reserved3[3];
  UCHAR      EndLba[4];
  UCHAR      ReadSpeed[4];
  UCHAR      WriteSpeed[4];
} CDROM_WRITE_SPEED_DESCRIPTOR, *PCDROM_WRITE_SPEED_DESCRIPTOR;
```

## Members


`MixedReadWrite`

The MixedReadWrite (MRW) field corresponds to the MRW bit of the Write Speed Descriptor in the MultiMedia Command Set - 6 (MMC-6)
specification. This field indicates that it is suitable for a mixture of streaming read and write requests (overwrite mode). The <a href="https://msdn.microsoft.com/library/windows/hardware/gg441244">STREAMING_CONTROL_REQUEST_TYPE</a>   enumeration specifies the type of request.

`Exact`

The Exact field indicates whether the logical unit can perform the recording operation specified by CDM_WRITE_SPEED_DESCRIPTOR
on the whole medium mounted. This field corresponds to the Exact bit of the Write Speed Descriptor.

`Reserved1`

Reserved fields.

`WriteRotationControl`

The WriteRotationControl (WRC) field specifies the type of the rotation control for the medium.

`Reserved2`

Reserved fields.

`Reserved3`

Reserved fields.

`EndLba`

The End Logical Block Address (EndLBA) field indicates the capacity of the medium if a medium is mounted. It corresponds to the EndLBA field of the Write Speed Descriptor.

`ReadSpeed`

The ReadSpeed field indicates the lowest read performance data of all blocks (in kilobytes per second).

`WriteSpeed`

The WriteSpeed field indicates the lowest write performance data of all blocks (in kilobytes per second).

## Remarks
The fields in the  <b>CDROM_WRITE_SPEED_DESCRIPTOR</b> structure correspond to the fields defined in the MultiMedia Command Set - 6 (MMC-6)
specification for the Write Speed Descriptor.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/gg441242">IOCTL_CDROM_GET_PERFORMANCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/gg441244">STREAMING_CONTROL_REQUEST_TYPE</a>