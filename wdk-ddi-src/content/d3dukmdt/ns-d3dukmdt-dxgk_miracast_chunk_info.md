---
UID: NS:d3dukmdt.DXGK_MIRACAST_CHUNK_INFO
title: DXGK_MIRACAST_CHUNK_INFO
author: windows-driver-content
description: Contains info about a specified wireless display (Miracast) encode chunk.
old-location: display\dxgk_miracast_chunk_info.htm
old-project: display
ms.assetid: 4A5413AD-A2EB-4772-89BF-867C30E0CD10
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_MIRACAST_CHUNK_INFO, DXGK_MIRACAST_CHUNK_INFO structure [Display Devices], d3dukmdt/DXGK_MIRACAST_CHUNK_INFO, display.dxgk_miracast_chunk_info
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h, D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dukmdt.h
api_name:
-	DXGK_MIRACAST_CHUNK_INFO
product:
- Windows
targetos: Windows
req.typenames: DXGK_MIRACAST_CHUNK_INFO
---

# DXGK_MIRACAST_CHUNK_INFO structure
Contains info about a specified wireless display (Miracast) encode chunk.

## Syntax
```
typedef struct DXGK_MIRACAST_CHUNK_INFO {
  DXGK_MIRACAST_CHUNK_TYPE ChunkType;
  DXGK_MIRACAST_CHUNK_ID   ChunkId;
  UINT                     ProcessingTime;
  UINT                     EncodeRate;
};
```

## Members


`ChunkType`

The type of chunk that is to be processed, specified as a <a href="https://msdn.microsoft.com/library/windows/hardware/dn322057">DXGK_MIRACAST_CHUNK_TYPE</a> enumeration value.

`ChunkId`

The identifier for this chunk, of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn322055">DXGK_MIRACAST_CHUNK_ID</a>.

`ProcessingTime`

The time, in microseconds, that it took to process this chunk.

`EncodeRate`

The encode bit rate, in kilobits per second, that the display miniport driver reported for this chunk.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dukmdt.h (include D3dukmdt.h, D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn322055">DXGK_MIRACAST_CHUNK_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn322057">DXGK_MIRACAST_CHUNK_TYPE</a>