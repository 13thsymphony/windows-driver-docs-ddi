---
UID: NS:lamp.LAMP_CAPABILITIES_WHITE
title: LAMP_CAPABILITIES_WHITE
author: windows-driver-content
description: This structure is the I/O parameter type of IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE.
old-location: stream\lamp_capabilities_white.htm
old-project: stream
ms.assetid: F407B953-8B03-4053-A5F4-3E96E9F9645E
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: LAMP_CAPABILITIES_WHITE, LAMP_CAPABILITIES_WHITE structure [Streaming Media Devices], lamp/LAMP_CAPABILITIES_WHITE, stream.lamp_capabilities_white
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	lamp.h
api_name:
-	LAMP_CAPABILITIES_WHITE
product: Windows
targetos: Windows
req.typenames: LAMP_CAPABILITIES_WHITE
---

# LAMP_CAPABILITIES_WHITE structure
This structure is the I/O parameter type of <b>IOCTL_LAMP_{GET|SET}_INTENSITY_WHITE</b>.

## Syntax
```
typedef struct LAMP_CAPABILITIES_WHITE {
  BOOLEAN IsLightIntensityAdjustable;
};
```

## Members


`IsLightIntensityAdjustable`

If this field evaluates <b>TRUE</b>, a client can get/set light intensity by calling <a href="https://msdn.microsoft.com/9B9FD4A1-F005-4CB8-80E3-D8AA74F6B9FB">IOCTL_LAMP_GET_INTENSITY_WHITE</a>  and <a href="https://msdn.microsoft.com/library/windows/hardware/dn925078">IOCTL_LAMP_SET_INTENSITY_WHITE</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | lamp.h |