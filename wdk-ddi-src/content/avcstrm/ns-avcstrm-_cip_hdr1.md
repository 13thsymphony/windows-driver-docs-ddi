---
UID: NS:avcstrm._CIP_HDR1
title: "_CIP_HDR1"
author: windows-driver-content
description: The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair).
old-location: stream\cip_hdr1.htm
old-project: stream
ms.assetid: 15450f33-cb86-4c1d-87d7-2d77a1d66a81
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PCIP_HDR1, CIP_HDR1, CIP_HDR1 structure [Streaming Media Devices], PCIP_HDR1, PCIP_HDR1 structure pointer [Streaming Media Devices], _CIP_HDR1, avcsref_bfb761c5-6eb2-459a-b75f-32c5e2d11700.xml, avcstrm/CIP_HDR1, avcstrm/PCIP_HDR1, stream.cip_hdr1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: avcstrm.h
req.include-header: Avcstrm.h
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
-	avcstrm.h
api_name:
-	CIP_HDR1
product: Windows
targetos: Windows
req.typenames: CIP_HDR1, *PCIP_HDR1
---

# _CIP_HDR1 structure
The CIP_HDR1 structure describes the generic data structure of the two quadlet CIP headers (first quadlet of the pair).

## Syntax
```
typedef struct _CIP_HDR1 {
  ULONG  : 8 DBC;
  ULONG  : 2 Rsv00;
  ULONG  : 1 SPH;
  ULONG  : 3 QPC;
  ULONG  : 2 FN;
  ULONG  : 8 DBS;
  ULONG  : 6 SID;
  ULONG  : 2 Bit00;
} CIP_HDR1, *PCIP_HDR1;
```

## Members


`DBC`

Data block counter. This is not used by subunit driver. It must be set to 0.

`Rsv00`

Reserved bits. Do not use this. It must be 0:0.

`SPH`

Specifies a source packet header. A value of 1 indicates the presence of a source packet header. A value of 0 indicates no source packet header.

`QPC`

Quadlet padding count (0..7 quadlets).

`FN`

Specifies the fractional number.

`DBS`

Specifies the data block size in quadlets.

`SID`

Specifies the source node ID (ID of transmitter). Not used by the subunit driver. Must be set to 0.

`Bit00`

Must be set to 0:0.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avcstrm.h (include Avcstrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557669">CIP_HDR2_FDF</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557672">CIP_HDR2_MPEGTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557676">CIP_HDR2_SYT</a>