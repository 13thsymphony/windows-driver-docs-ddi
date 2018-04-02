---
UID: NS:ksmedia.tagKS_DATAFORMAT_VBIINFOHEADER
title: tagKS_DATAFORMAT_VBIINFOHEADER
author: windows-driver-content
description: The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.
old-location: stream\ks_dataformat_vbiinfoheader.htm
old-project: stream
ms.assetid: 597b081f-d2ff-4e20-b352-2082f1ef4d45
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER structure [Streaming Media Devices], PKS_DATAFORMAT_VBIINFOHEADER, PKS_DATAFORMAT_VBIINFOHEADER structure pointer [Streaming Media Devices], ksmedia/KS_DATAFORMAT_VBIINFOHEADER, ksmedia/PKS_DATAFORMAT_VBIINFOHEADER, stream.ks_dataformat_vbiinfoheader, tagKS_DATAFORMAT_VBIINFOHEADER, vidcapstruct_67cdb187-7d2b-464b-a871-6b2f18a9839f.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
api_name:
-	KS_DATAFORMAT_VBIINFOHEADER
product: Windows
targetos: Windows
req.typenames: KS_DATAFORMAT_VBIINFOHEADER, *PKS_DATAFORMAT_VBIINFOHEADER
---

# tagKS_DATAFORMAT_VBIINFOHEADER structure
The KS_DATAFORMAT_VBIINFOHEADER structure describes a vertical blanking interval (VBI) stream.

## Syntax
```
typedef struct tagKS_DATAFORMAT_VBIINFOHEADER {
  KSDATAFORMAT     DataFormat;
  KS_VBIINFOHEADER VBIInfoHeader;
} *PKS_DATAFORMAT_VBIINFOHEADER, KS_DATAFORMAT_VBIINFOHEADER;
```

## Members


`DataFormat`

Specifies the data format being proposed.

`VBIInfoHeader`

Describes VBI-specific information about the proposed connection.

## Remarks
This structure is used when a connection to a VBI pin is being proposed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561656">KSDATAFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567692">KS_VBIINFOHEADER</a>