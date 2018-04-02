---
UID: NS:bdamedia.tagBDA_TRANSPORT_INFO
title: tagBDA_TRANSPORT_INFO
author: windows-driver-content
description: The BDA_TRANSPORT_INFO structure describes formatting for a stream connection.
old-location: stream\bda_transport_info.htm
old-project: stream
ms.assetid: 995a1d2f-8e2b-426e-a08c-283124ce905e
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PBDA_TRANSPORT_INFO, BDA_TRANSPORT_INFO, BDA_TRANSPORT_INFO structure [Streaming Media Devices], PBDA_TRANSPORT_INFO, PBDA_TRANSPORT_INFO structure pointer [Streaming Media Devices], bdamedia/BDA_TRANSPORT_INFO, bdamedia/PBDA_TRANSPORT_INFO, bdaref_3ee17c26-da8b-4d04-87fc-6c9912de349d.xml, stream.bda_transport_info, tagBDA_TRANSPORT_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
-	bdamedia.h
api_name:
-	BDA_TRANSPORT_INFO
product: Windows
targetos: Windows
req.typenames: BDA_TRANSPORT_INFO, *PBDA_TRANSPORT_INFO
---

# tagBDA_TRANSPORT_INFO structure
The BDA_TRANSPORT_INFO structure describes formatting for a stream connection.

## Syntax
```
typedef struct tagBDA_TRANSPORT_INFO {
  ULONG          ulcbPhyiscalPacket;
  ULONG          ulcbPhyiscalFrame;
  ULONG          ulcbPhyiscalFrameAlignment;
  REFERENCE_TIME AvgTimePerFrame;
} *PBDA_TRANSPORT_INFO, BDA_TRANSPORT_INFO;
```

## Members


`ulcbPhyiscalPacket`

Size, in bytes, of a physical packet (for example, the size of a satellite link payload).

`ulcbPhyiscalFrame`

Size, in bytes, of each physical frame (0 indicates no hardware requirement).

`ulcbPhyiscalFrameAlignment`

Capture buffer alignment in bytes (0 and 1 indicate no alignment requirements).

`AvgTimePerFrame`

REFERENCE TIME value that indicates the video frame's average display time, in 100-nanosecond units.

## Remarks
A BDA_TRANSPORT_INFO structure in conjunction with a KSDATARANGE structure makes up a KS_DATARANGE_BDA_TRANSPORT data range. A data range describes a range of data formats. 

Pins of filters specify the data ranges they support to enable stream connections to pins of other filters that also support those data ranges.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdamedia.h (include Bdamedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563533">KSPIN_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567346">KS_DATARANGE_BDA_TRANSPORT</a>