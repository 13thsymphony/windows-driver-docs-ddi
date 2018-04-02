---
UID: NS:wdm._CM_FLOPPY_DEVICE_DATA
title: "_CM_FLOPPY_DEVICE_DATA"
author: windows-driver-content
description: The CM_FLOPPY_DEVICE_DATA structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process.
old-location: kernel\cm_floppy_device_data.htm
old-project: kernel
ms.assetid: 0ef0d242-4ed6-4c48-85b8-0fc87d3fe39b
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PCM_FLOPPY_DEVICE_DATA, CM_FLOPPY_DEVICE_DATA, CM_FLOPPY_DEVICE_DATA structure [Kernel-Mode Driver Architecture], PCM_FLOPPY_DEVICE_DATA, PCM_FLOPPY_DEVICE_DATA structure pointer [Kernel-Mode Driver Architecture], _CM_FLOPPY_DEVICE_DATA, kernel.cm_floppy_device_data, kstruct_a_7ec8badb-4d88-479e-b0dc-ce88660b8449.xml, wdm/CM_FLOPPY_DEVICE_DATA, wdm/PCM_FLOPPY_DEVICE_DATA"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	CM_FLOPPY_DEVICE_DATA
product:
- Windows
targetos: Windows
req.typenames: CM_FLOPPY_DEVICE_DATA, *PCM_FLOPPY_DEVICE_DATA
req.product: Windows 10 or later.
---

# _CM_FLOPPY_DEVICE_DATA structure
The <b>CM_FLOPPY_DEVICE_DATA</b> structure defines a device-type-specific data record that is stored in the \\Registry\Machine\Hardware\Description tree for a floppy controller if the system can collect this information during the boot process.

## Syntax
```
typedef struct _CM_FLOPPY_DEVICE_DATA {
  USHORT Version;
  USHORT Revision;
  CHAR   Size[8];
  ULONG  MaxDensity;
  ULONG  MountDensity;
  UCHAR  StepRateHeadUnloadTime;
  UCHAR  HeadLoadTime;
  UCHAR  MotorOffTime;
  UCHAR  SectorLengthCode;
  UCHAR  SectorPerTrack;
  UCHAR  ReadWriteGapLength;
  UCHAR  DataTransferLength;
  UCHAR  FormatGapLength;
  UCHAR  FormatFillCharacter;
  UCHAR  HeadSettleTime;
  UCHAR  MotorSettleTime;
  UCHAR  MaximumTrackValue;
  UCHAR  DataTransferRate;
} CM_FLOPPY_DEVICE_DATA, *PCM_FLOPPY_DEVICE_DATA;
```

## Members


`Version`

The version number of this structure.

`Revision`

The revision of this structure.

`Size`

The floppy disk density size.

`MaxDensity`

The maximum density.

`MountDensity`

The mount density.

`StepRateHeadUnloadTime`

The step rate head unload time in milliseconds.

`HeadLoadTime`

The head load time in milliseconds.

`MotorOffTime`

The motor off time in seconds.

`SectorLengthCode`

Indicates the sector size as an exponent in the formula ((2**<i>code</i>) * 128).

`SectorPerTrack`

The number of sectors per track.

`ReadWriteGapLength`

The read/write gap length, in bytes.

`DataTransferLength`

The data transfer length, in bytes, not including the synchronization field.

`FormatGapLength`

The format gap length, in bytes.

`FormatFillCharacter`

The format fill character.

`HeadSettleTime`

The head settle time in milliseconds.

`MotorSettleTime`

The motor settle time in milliseconds.

`MaximumTrackValue`

The maximum track number on the media. Track numbers are zero-based values.

`DataTransferRate`

The value written to the Datarate register before accessing the media.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="https://msdn.microsoft.com/96bf7bab-b8f5-439c-8717-ea6956ed0213">CM_PARTIAL_RESOURCE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549453">IoQueryDeviceDescription</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549616">IoReportResourceUsage</a>