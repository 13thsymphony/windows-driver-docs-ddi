---
UID: NS:ntdddisk._REASSIGN_BLOCKS_EX
title: "_REASSIGN_BLOCKS_EX"
author: windows-driver-content
description: The REASSIGN_BLOCKS_EX structure is used in conjunction with the IOCTL_DISK_REASSIGN_BLOCKS_EX request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.
old-location: storage\reassign_blocks_ex.htm
old-project: storage
ms.assetid: D1BE17A0-39F1-496A-AD53-46A3F136D793
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX, PREASSIGN_BLOCKS_EX structure pointer [Storage Devices], REASSIGN_BLOCKS_EX, REASSIGN_BLOCKS_EX structure [Storage Devices], _REASSIGN_BLOCKS_EX, ntdddisk/PREASSIGN_BLOCKS_EX, ntdddisk/REASSIGN_BLOCKS_EX, storage.reassign_blocks_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
-	ntdddisk.h
api_name:
-	REASSIGN_BLOCKS_EX
product: Windows
targetos: Windows
req.typenames: REASSIGN_BLOCKS_EX, *PREASSIGN_BLOCKS_EX
---

# _REASSIGN_BLOCKS_EX structure
The <b>REASSIGN_BLOCKS_EX</b> structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/jj602797">IOCTL_DISK_REASSIGN_BLOCKS_EX</a> request to instruct a disk device to reassign the block numbers of the indicated bad blocks to good blocks.

## Syntax
```
typedef struct _REASSIGN_BLOCKS_EX {
  USHORT        Reserved;
  USHORT        Count;
  LARGE_INTEGER BlockNumber[1];
} *PREASSIGN_BLOCKS_EX, REASSIGN_BLOCKS_EX;
```

## Members


`Reserved`

Reserved for system use.

`Count`

Contains the number of blocks in the array pointed to by <b>BlockNumber</b> to reassign.

`BlockNumber`

Contains an array of block numbers corresponding to damaged blocks. These numbers will be reassigned to good blocks taken from the device's spare block pool.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | ntdddisk.h (include Ntdddisk.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/jj602797">IOCTL_DISK_REASSIGN_BLOCKS_EX</a>