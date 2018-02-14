---
UID: NS:lamp.LAMP_INTENSITY_WHITE
title: LAMP_INTENSITY_WHITE
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_GET_INTENSITY_WHITE and IOCTL_LAMP_SET_INTENSITY_WHITE.
old-location: stream\lamp_intensity_white.htm
old-project: stream
ms.assetid: BDE53311-589F-4458-9510-1B02F1BD0289
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: LAMP_INTENSITY_WHITE structure [Streaming Media Devices], lamp/LAMP_INTENSITY_WHITE, stream.lamp_intensity_white, LAMP_INTENSITY_WHITE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: lamp.h
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	lamp.h
apiname:
-	LAMP_INTENSITY_WHITE
product: Windows
targetos: Windows
req.typenames: LAMP_INTENSITY_WHITE
---

# LAMP_INTENSITY_WHITE structure
This structure is the I/O parameter type of <a href="..\lamp\ni-lamp-ioctl_lamp_get_intensity_white.md">IOCTL_LAMP_GET_INTENSITY_WHITE</a> and <a href="..\lamp\ni-lamp-ioctl_lamp_set_intensity_white.md">IOCTL_LAMP_SET_INTENSITY_WHITE</a>.

## Syntax
````
typedef struct LAMP_INTENSITY_WHITE {
  BYTE Value;
} LAMP_INTENSITY_WHITE;
````

## Members


`Value`

White light intensity in percentage (0-100).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | lamp.h |