---
UID: NS:ksmedia._tagKSTOPOLOGY_ENDPOINTID
title: "_tagKSTOPOLOGY_ENDPOINTID"
author: windows-driver-content
description: The KSTOPOLOGY_ENDPOINTID structure specifies the name and the pin ID of a topology endpoint.
old-location: audio\kstopology_endpointid.htm
old-project: audio
ms.assetid: A84BE3D6-7D2A-4123-979B-F6E1CA8C8B23
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSTOPOLOGY_ENDPOINTID, KSTOPOLOGY_ENDPOINTID, KSTOPOLOGY_ENDPOINTID structure [Audio Devices], PKSTOPOLOGY_ENDPOINTID, PKSTOPOLOGY_ENDPOINTID structure pointer [Audio Devices], _tagKSTOPOLOGY_ENDPOINTID, audio.kstopology_endpointid, ksmedia/KSTOPOLOGY_ENDPOINTID, ksmedia/PKSTOPOLOGY_ENDPOINTID"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10,Windows 10 Mobile
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ksmedia.h
api_name:
-	KSTOPOLOGY_ENDPOINTID
product: Windows
targetos: Windows
req.typenames: KSTOPOLOGY_ENDPOINTID, *PKSTOPOLOGY_ENDPOINTID
---

# _tagKSTOPOLOGY_ENDPOINTID structure
The <b>KSTOPOLOGY_ENDPOINTID</b> structure specifies the name and the pin ID of a topology endpoint.

## Syntax
````
typedef struct _tagKSTOPOLOGY_ENDPOINTID {
  WCHAR TopologyName[MAX_PATH];
  ULONG PinId;
} KSTOPOLOGY_ENDPOINTID, *PKSTOPOLOGY_ENDPOINTID;
````

## Members


`TopologyName`

The name of the topology endpoint.

`PinId`

The pin ID of the topology endpoint.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10,Windows 10 Mobile Windows 10,Windows 10 Mobile |
| **Header** | ksmedia.h |

## See Also

<a href="..\ksmedia\ns-ksmedia-_tagkstopology_endpointidpair.md">KSTOPOLOGY_ENDPOINTIDPAIR</a>