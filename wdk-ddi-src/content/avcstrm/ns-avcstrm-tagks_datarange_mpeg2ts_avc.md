---
UID: NS:avcstrm.tagKS_DATARANGE_MPEG2TS_AVC
title: tagKS_DATARANGE_MPEG2TS_AVC
author: windows-driver-content
description: The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats.
old-location: stream\ks_datarange_mpeg2ts_avc.htm
old-project: stream
ms.assetid: 3e19439d-397c-4c22-823c-aa53c456d7b9
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKS_DATARANGE_MPEG2TS_AVC, KS_DATARANGE_MPEG2TS_AVC, KS_DATARANGE_MPEG2TS_AVC structure [Streaming Media Devices], PKS_DATARANGE_MPEG2TS_AVC, PKS_DATARANGE_MPEG2TS_AVC structure pointer [Streaming Media Devices], avcsref_604304aa-f90b-4897-a134-c05eff1240aa.xml, avcstrm/KS_DATARANGE_MPEG2TS_AVC, avcstrm/PKS_DATARANGE_MPEG2TS_AVC, stream.ks_datarange_mpeg2ts_avc, tagKS_DATARANGE_MPEG2TS_AVC"
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
-	KS_DATARANGE_MPEG2TS_AVC
product: Windows
targetos: Windows
req.typenames: KS_DATARANGE_MPEG2TS_AVC, *PKS_DATARANGE_MPEG2TS_AVC
---

# tagKS_DATARANGE_MPEG2TS_AVC structure
The KS_DATARANGE_MPEG2TS_AVC structure stores a range of AV/C MPEG2 formats.

## Syntax
````
typedef struct tagKS_DATARANGE_MPEG2TS_AVC {
  KSDATARANGE       DataRange;
  AVCPRECONNECTINFO ConnectInfo;
} KS_DATARANGE_MPEG2TS_AVC, *PKS_DATARANGE_MPEG2TS_AVC;
````

## Members


`DataRange`

Specifies the range of supported AV/C MPEG2 formats.

`ConnectInfo`

Specifies the AV/C preconnection info.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | avcstrm.h (include Avcstrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561658">KSDATARANGE</a>



<a href="..\avc\ns-avc-_avcpreconnectinfo.md">AVCPRECONNECTINFO</a>