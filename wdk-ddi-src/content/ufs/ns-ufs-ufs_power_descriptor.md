---
UID: NS:ufs.UFS_POWER_DESCRIPTOR
title: UFS_POWER_DESCRIPTOR
author: windows-driver-content
description: UFS_POWER_DESCRIPTOR contains information about the power capabilities and power states of the device.
old-location: storage\ufs_power_descriptor.htm
old-project: storage
ms.assetid: FCF9DCD1-2C04-47E3-97C5-7ACC28B28C6C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: PUFS_POWER_DESCRIPTOR structure pointer [Storage Devices], ufs/PUFS_POWER_DESCRIPTOR, *PUFS_POWER_DESCRIPTOR, UFS_POWER_DESCRIPTOR, ufs/UFS_POWER_DESCRIPTOR, storage.ufs_power_descriptor, PUFS_POWER_DESCRIPTOR, UFS_POWER_DESCRIPTOR structure [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ufs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ufs.h
apiname:
-	UFS_POWER_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_POWER_DESCRIPTOR, *PUFS_POWER_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_POWER_DESCRIPTOR structure
<b>UFS_POWER_DESCRIPTOR </b>contains information about the power capabilities and power states of the device.

## Syntax
````
typedef struct _UFS_POWER_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR wActiveICCLevelsVCC[32];
  UCHAR wActiveICCLevelsVCCQ[32];
  UCHAR wActiveICCLevelsVCCQ2[32];
} UFS_POWER_DESCRIPTOR, *PUFS_POWER_DESCRIPTOR;
````

## Members


`bDescriptorIDN`

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_POWER_IDN</b>.

`bLength`

Specifies the length, in bytes, of this descriptor.

`wActiveICCLevelsVCC`

Specifies the maximum VCC current value for
each UFS_bActiveICCLevel, based on the index value.

`wActiveICCLevelsVCCQ`

Specifies the maximum VCCQ current value for
each UFS_bActiveICCLevel, based on the index value.

`wActiveICCLevelsVCCQ2`

Specifies the maximum VCCQ current value for
each UFS_bActiveICCLevel, based on the index value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ufs.h |