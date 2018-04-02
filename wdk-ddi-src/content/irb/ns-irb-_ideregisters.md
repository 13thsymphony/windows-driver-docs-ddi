---
UID: NS:irb._IDEREGISTERS
title: "_IDEREGISTERS"
author: windows-driver-content
description: The IDEREGISTERS structure is used to report the contents of the IDE controller registers.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ideregisters.htm
old-project: storage
ms.assetid: a3df8ce0-4414-49d1-a02c-3f5a3efc0de2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PIDEREGISTERS, IDEREGISTERS, IDEREGISTERS structure [Storage Devices], PIDEREGISTERS, PIDEREGISTERS structure pointer [Storage Devices], _IDEREGISTERS, irb/IDEREGISTERS, irb/PIDEREGISTERS, storage.ideregisters, structs-ATA_8e024553-553c-4a64-9f74-7259f530b3b5.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: irb.h
req.include-header: Irb.h
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
-	irb.h
api_name:
-	IDEREGISTERS
product:
- Windows
targetos: Windows
req.typenames: IDEREGISTERS, *PIDEREGISTERS
---

# _IDEREGISTERS structure
The IDEREGISTERS structure is used to report the contents of the IDE controller registers.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
```
typedef struct _IDEREGISTERS {
  UCHAR bFeaturesReg;
  UCHAR bSectorCountReg;
  UCHAR bSectorNumberReg;
  UCHAR bCylLowReg;
  UCHAR bCylHighReg;
  UCHAR bDriveHeadReg;
  UCHAR bCommandReg;
  UCHAR bReserved;
} *PIDEREGISTERS, IDEREGISTERS;
```

## Members


`bFeaturesReg`

Specifies the contents of the ATA features register.

`bSectorCountReg`

Specifies the contents of the ATA Sector Count register.

`bSectorNumberReg`

Specifies the contents of the ATA Sector Number register.

`bCylLowReg`

Specifies the contents of the ATA Cylinder Low register.

`bCylHighReg`

Specifies the contents of the ATA Cylinder High register.

`bDriveHeadReg`

Specifies the contents of the ATA Device/Head register.

`bCommandReg`

Specifies the contents of the ATA Command register.

`bReserved`

Reserved for future use. The miniport driver shall not use this field.

## Remarks
The information reported in the IDEREGISTERS structure is intended to be a superset of the information contained in <a href="https://msdn.microsoft.com/library/windows/hardware/ff559015">IDEREGS</a>. Microsoft might expand the contents of the IDEREGISTERS structure in the future. If you need a structure whose size is stable across different versions of the operating system, you should use <b>IDEREGS</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | irb.h (include Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559015">IDEREGS</a>