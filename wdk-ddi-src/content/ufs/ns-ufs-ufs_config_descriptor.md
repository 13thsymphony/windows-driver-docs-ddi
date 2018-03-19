---
UID: NS:ufs.UFS_CONFIG_DESCRIPTOR
title: UFS_CONFIG_DESCRIPTOR
author: windows-driver-content
description: The UFS_CONFIG_DESCRIPTOR structure describes the modifiable values of the default device configuration set by the manufacturer.
old-location: storage\ufs_config_descriptor.htm
old-project: storage
ms.assetid: B65A2268-6959-4630-97DA-C0CFD37D9174
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR, PUFS_CONFIG_DESCRIPTOR structure pointer [Storage Devices], UFS_CONFIG_DESCRIPTOR, UFS_CONFIG_DESCRIPTOR structure [Storage Devices], storage.ufs_config_descriptor, ufs/PUFS_CONFIG_DESCRIPTOR, ufs/UFS_CONFIG_DESCRIPTOR"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ufs.h
api_name:
-	UFS_CONFIG_DESCRIPTOR
product: Windows
targetos: Windows
req.typenames: UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_CONFIG_DESCRIPTOR structure
The <b>UFS_CONFIG_DESCRIPTOR</b> structure describes the modifiable values of the default device configuration set by the manufacturer.

## Syntax
````
typedef struct _UFS_CONFIG_DESCRIPTOR {
  UCHAR                       bLength;
  UCHAR                       bDescriptorIDN;
  UCHAR                       Reserved1;
  UCHAR                       bBootEnable;
  UCHAR                       bDescrAccessEn;
  UCHAR                       bInitPowerMode;
  UCHAR                       bHighPriorityLUN;
  UCHAR                       bSecureRemovalType;
  UCHAR                        bInitActiveICCLevel;
  UCHAR                       wPeriodicRTCUpdate[2];
  UCHAR                        Reserved2[5];
   UFS_UNIT_CONFIG_DESCRIPTOR UnitConfig[UFS_MAX_NUM_LU];
} UFS_CONFIG_DESCRIPTOR, *PUFS_CONFIG_DESCRIPTOR;
````

## Members


`bLength`

Specifies the size, in bytes, of this descriptor.

`bDescriptorIDN`

Specifies the Configuration Descriptor Type Identifier. This descriptor will have a value of <b>UFS_DESC_CONFIGURATION_IDN</b>.

`Reserved1`

Reserved for future use.

`bBootEnable`

Specifies if a device's boot feature is enabled.

`bDescrAccessEn`

Enables access to the Device Descriptor after the
partial initialization phase of the boot sequence.

`bInitPowerMode`

Specifies the power mode after device initialization
or hardware reset.

`bHighPriorityLUN`

<b>bHighPriorityLUN</b> configures the high priority logical unit.

`bSecureRemovalType`

Configures the secure removal type.

`bInitActiveICCLevel`

Configures the ICC level in Active mode after device
initialization or hardware reset.

`wPeriodicRTCUpdate`

Specifies the frequency and method of real-time clock updates.

`Reserved2`

Reserved for future use.

`UnitConfig`

Contains the configurable parameters of the Unit Descriptor.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ufs.h |

## See Also

<a href="..\ufs\ns-ufs-ufs_unit_config_descriptor.md">UFS_UNIT_CONFIG_DESCRIPTOR</a>