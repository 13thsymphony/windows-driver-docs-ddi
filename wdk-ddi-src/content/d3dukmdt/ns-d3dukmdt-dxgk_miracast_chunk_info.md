---
UID : NS:d3dukmdt.DXGK_MIRACAST_CHUNK_INFO
title : DXGK_MIRACAST_CHUNK_INFO
author : windows-driver-content
description : Contains info about a specified wireless display (Miracast) encode chunk.
old-location : display\dxgk_miracast_chunk_info.htm
old-project : display
ms.assetid : 4A5413AD-A2EB-4772-89BF-867C30E0CD10
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : DXGK_MIRACAST_CHUNK_INFO structure [Display Devices], DXGK_MIRACAST_CHUNK_INFO, display.dxgk_miracast_chunk_info, d3dukmdt/DXGK_MIRACAST_CHUNK_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dukmdt.h
req.include-header : D3dukmdt.h, D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_MIRACAST_CHUNK_INFO
---

# DXGK_MIRACAST_CHUNK_INFO structure
Contains info about a specified wireless display (Miracast) encode chunk.

## Syntax
````
typedef struct {
  DXGK_MIRACAST_CHUNK_TYPE ChunkType;
  MIRACAST_CHUNK_ID        ChunkId;
  UINT                     ProcessingTime;
  UINT                     EncodeRate;
} DXGK_MIRACAST_CHUNK_INFO;
````

## Members


`ChunkId`

The identifier for this chunk, of type <a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_id.md">DXGK_MIRACAST_CHUNK_ID</a>.

`ChunkType`

The type of chunk that is to be processed, specified as a <a href="..\d3dukmdt\ne-d3dukmdt-_dxgk_miracast_chunk_type.md">DXGK_MIRACAST_CHUNK_TYPE</a> enumeration value.

`EncodeRate`

The encode bit rate, in kilobits per second, that the display miniport driver reported for this chunk.

`ProcessingTime`

The time, in microseconds, that it took to process this chunk.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dukmdt.h (include D3dukmdt.h, D3dkmddi.h) |

## See Also

<a href="..\d3dukmdt\ne-d3dukmdt-_dxgk_miracast_chunk_type.md">DXGK_MIRACAST_CHUNK_TYPE</a>

<a href="..\d3dukmdt\ns-d3dukmdt-dxgk_miracast_chunk_id.md">DXGK_MIRACAST_CHUNK_ID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MIRACAST_CHUNK_INFO structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>