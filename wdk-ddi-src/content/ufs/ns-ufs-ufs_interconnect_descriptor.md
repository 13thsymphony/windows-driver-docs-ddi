---
UID: NS:ufs.UFS_INTERCONNECT_DESCRIPTOR
title: UFS_INTERCONNECT_DESCRIPTOR
author: windows-driver-content
description: UFS_INTERCONNECT_DESCRIPTOR contains the MIPI M-PHY® specification version number and the MIPI 6338 UniPro℠ specification version number.
old-location: storage\ufs_interconnect_descriptor.htm
old-project: storage
ms.assetid: 6C6EAA96-40E9-467F-903B-AE44CE5B77CF
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUFS_INTERCONNECT_DESCRIPTOR, PUFS_INTERCONNECT_DESCRIPTOR, PUFS_INTERCONNECT_DESCRIPTOR structure pointer [Storage Devices], UFS_INTERCONNECT_DESCRIPTOR, UFS_INTERCONNECT_DESCRIPTOR structure [Storage Devices], storage.ufs_interconnect_descriptor, ufs/PUFS_INTERCONNECT_DESCRIPTOR, ufs/UFS_INTERCONNECT_DESCRIPTOR"
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
-	UFS_INTERCONNECT_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: UFS_INTERCONNECT_DESCRIPTOR, *PUFS_INTERCONNECT_DESCRIPTOR
req.product: Windows 10 or later.
---

# UFS_INTERCONNECT_DESCRIPTOR structure
<b>UFS_INTERCONNECT_DESCRIPTOR</b> contains the MIPI M-PHY® specification version number and the MIPI
6338 UniPro℠ specification version number.

## Syntax
```
typedef struct UFS_INTERCONNECT_DESCRIPTOR {
  UCHAR bLength;
  UCHAR bDescriptorIDN;
  UCHAR bcdUniproVersion[2];
  UCHAR bcdMphyVersion[2];
} *PUFS_INTERCONNECT_DESCRIPTOR, UFS_INTERCONNECT_DESCRIPTOR;
```

## Members


`bLength`

Specifies the length, in bytes, of this descriptor.

`bDescriptorIDN`

Specifies the type of the descriptor. This descriptor will have a value of <b>UFS_DESC_INTERCONNECT_IDN</b>.

`bcdUniproVersion`

Specifies the MIPI UniPro℠ version number in Binary Coded Decimal (BCD) format.

`bcdMphyVersion`

Specifies the MIPI M-PHY® version number in BCD format.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows 10, version 1709 |
| **Header** | ufs.h |