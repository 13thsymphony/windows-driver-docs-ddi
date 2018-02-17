---
UID: NS:irb._IDE_ACCESS_RANGE
title: "_IDE_ACCESS_RANGE"
author: windows-driver-content
description: The IDE_ACCESS_RANGE structure contains the address ranges allocated for an IDE controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_access_range.htm
old-project: storage
ms.assetid: e81441a2-0659-4d32-97f4-415abef6c87a
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: PIDE_ACCESS_RANGE, *PIDE_ACCESS_RANGE, _IDE_ACCESS_RANGE, structs-ATA_6c50e733-2896-4052-a867-ae2c9d119ff2.xml, irb/PIDE_ACCESS_RANGE, PIDE_ACCESS_RANGE structure pointer [Storage Devices], storage.ide_access_range, irb/IDE_ACCESS_RANGE, IDE_ACCESS_RANGE, IDE_ACCESS_RANGE structure [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	IDE_ACCESS_RANGE
product: Windows
targetos: Windows
req.typenames: IDE_ACCESS_RANGE, *PIDE_ACCESS_RANGE
---

# _IDE_ACCESS_RANGE structure
The IDE_ACCESS_RANGE structure contains the address ranges allocated for an IDE controller.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef struct _IDE_ACCESS_RANGE {
  IDE_PHYSICAL_ADDRESS RangeStart;
  IDE_PHYSICAL_ADDRESS PhysicalRangeStart;
  ULONG                RangeLength;
  BOOLEAN              InMemory;
  UCHAR                Bar;
} IDE_ACCESS_RANGE, *PIDE_ACCESS_RANGE;
````

## Members


`Bar`

The number of the PCI Base Address Range that this resource was found in.

`InMemory`

Flag that indicates if this is a memory mapped resource. If cleared, this is an I/O port resource.

`PhysicalRangeStart`

Contains the physical starting address of the address range.

`RangeLength`

Contains the size, in bytes, of the range.

`RangeStart`

Contains the logical starting address of the address range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | irb.h (include Irb.h) |