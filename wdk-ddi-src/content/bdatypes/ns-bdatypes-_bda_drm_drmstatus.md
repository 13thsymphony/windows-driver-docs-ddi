---
UID: NS:bdatypes._BDA_DRM_DRMSTATUS
title: "_BDA_DRM_DRMSTATUS"
author: windows-driver-content
description: "."
old-location: stream\bda_drm_drmstatus.htm
old-project: stream
ms.assetid: EC287CF0-9B39-4412-849E-9F86EEE69365
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: "*PBDA_DRM_DRMSTATUS, _BDA_DRM_DRMSTATUS, bdatypes/BDA_DRM_DRMSTATUS, PBDA_DRM_DRMSTATUS, stream.bda_drm_drmstatus, BDA_DRM_DRMSTATUS, PBDA_DRM_DRMSTATUS structure pointer [Streaming Media Devices], BDA_DRM_DRMSTATUS structure [Streaming Media Devices], bdatypes/PBDA_DRM_DRMSTATUS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bdatypes.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Bdatypes.h
apiname:
-	BDA_DRM_DRMSTATUS
product: Windows
targetos: Windows
req.typenames: BDA_DRM_DRMSTATUS, *PBDA_DRM_DRMSTATUS
---

# _BDA_DRM_DRMSTATUS structure


## Syntax
````
typedef struct _BDA_DRM_DRMSTATUS {
  PBDARESULT lResult;
  GUID       DRMuuid;
  ULONG      ulDrmUuidListStringSize;
  GUID       argbDrmUuidListString[MIN_DIMENSION];
} BDA_DRM_DRMSTATUS, *PBDA_DRM_DRMSTATUS;
````

## Members


`argbDrmUuidListString`



`DRMuuid`



`lResult`



`ulDrmUuidListStringSize`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | bdatypes.h |