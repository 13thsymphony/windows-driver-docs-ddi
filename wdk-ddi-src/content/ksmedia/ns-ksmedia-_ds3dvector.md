---
UID: NS:ksmedia._DS3DVECTOR
title: "_DS3DVECTOR"
author: windows-driver-content
description: The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components.
old-location: audio\ds3dvector.htm
old-project: audio
ms.assetid: 828bb255-4640-4508-866e-e3641ca05773
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PDS3DVECTOR, DS3DVECTOR, DS3DVECTOR structure [Audio Devices], PDS3DVECTOR, PDS3DVECTOR structure pointer [Audio Devices], _DS3DVECTOR, aud-prop_3e17b5ec-c2fc-4e6c-bff1-27be36e376c9.xml, audio.ds3dvector, ksmedia/DS3DVECTOR, ksmedia/PDS3DVECTOR"
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
-	DS3DVECTOR
product: Windows
targetos: Windows
req.typenames: DS3DVECTOR, *PDS3DVECTOR
---

# _DS3DVECTOR structure
The DS3DVECTOR structure contains three-dimensional position coordinates, position vector components, or velocity vector components.

## Syntax
````
typedef struct _DS3DVECTOR {
  union {
    FLOAT x;
    FLOAT dvX;
  };
  union {
    FLOAT y;
    FLOAT dvY;
  };
  union {
    FLOAT z;
    FLOAT dvZ;
  };
} DS3DVECTOR, *PDS3DVECTOR;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ksmedia\ns-ksmedia-ksds3d_listener_orientation.md">KSDS3D_LISTENER_ORIENTATION</a>



<a href="..\ksmedia\ns-ksmedia-ksds3d_buffer_all.md">KSDS3D_BUFFER_ALL</a>



<a href="..\ksmedia\ns-ksmedia-ksds3d_listener_all.md">KSDS3D_LISTENER_ALL</a>