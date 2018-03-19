---
UID: NS:ksmedia._tagKSTOPOLOGY_ENDPOINTIDPAIR
title: "_tagKSTOPOLOGY_ENDPOINTIDPAIR"
author: windows-driver-content
description: The KSTOPOLOGY_ENDPOINTIDPAIR structure specifies the render and capture endpoint IDs to use for the KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR property.
old-location: audio\kstopology_endpointidpair.htm
old-project: audio
ms.assetid: 556B56A6-1EF4-406B-A9FB-901C0CF24BC0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PKSTOPOLOGY_ENDPOINTIDPAIR, KSTOPOLOGY_ENDPOINTIDPAIR, KSTOPOLOGY_ENDPOINTIDPAIR structure [Audio Devices], PKSTOPOLOGY_ENDPOINTIDPAIR, PKSTOPOLOGY_ENDPOINTIDPAIR structure pointer [Audio Devices], _tagKSTOPOLOGY_ENDPOINTIDPAIR, audio.kstopology_endpointidpair, ksmedia/KSTOPOLOGY_ENDPOINTIDPAIR, ksmedia/PKSTOPOLOGY_ENDPOINTIDPAIR"
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
-	KSTOPOLOGY_ENDPOINTIDPAIR
product: Windows
targetos: Windows
req.typenames: KSTOPOLOGY_ENDPOINTIDPAIR, *PKSTOPOLOGY_ENDPOINTIDPAIR
---

# _tagKSTOPOLOGY_ENDPOINTIDPAIR structure
The <b>KSTOPOLOGY_ENDPOINTIDPAIR</b> structure specifies the render and capture endpoint IDs to use for the <a href="https://msdn.microsoft.com/library/windows/hardware/mt169874">KSPROPERTY_TELEPHONY_ENDPOINTIDPAIR</a> property.

## Syntax
````
typedef struct _tagKSTOPOLOGY_ENDPOINTIDPAIR {
  KSTOPOLOGY_ENDPOINTID RenderEndpoint;
  KSTOPOLOGY_ENDPOINTID CaptureEndpoint;
} KSTOPOLOGY_ENDPOINTIDPAIR, *PKSTOPOLOGY_ENDPOINTIDPAIR;
````

## Members


`RenderEndpoint`

Specifies the render endpoint ID.

`CaptureEndpoint`

Specifies the capture endpoint ID.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10,Windows 10 Mobile Windows 10,Windows 10 Mobile |
| **Header** | ksmedia.h |

## See Also

<a href="..\ksmedia\ns-ksmedia-_tagkstopology_endpointid.md">KSTOPOLOGY_ENDPOINTID</a>