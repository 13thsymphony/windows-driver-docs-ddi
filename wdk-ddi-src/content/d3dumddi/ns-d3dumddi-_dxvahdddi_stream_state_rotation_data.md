---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ROTATION_DATA
title: "_DXVAHDDDI_STREAM_STATE_ROTATION_DATA"
author: windows-driver-content
description: Describes stream-state data that specifies the clockwise rotation of the display output surface.
old-location: display\dxvahdddi_stream_state_rotation_data.htm
old-project: display
ms.assetid: 1c874df6-6b47-4501-9eaf-7c07f0172580
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVAHDDDI_STREAM_STATE_ROTATION_DATA, DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_ROTATION_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_ROTATION_DATA, display.dxvahdddi_stream_state_rotation_data
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dumddi.h
api_name:
-	DXVAHDDDI_STREAM_STATE_ROTATION_DATA
product: Windows
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ROTATION_DATA
---

# _DXVAHDDDI_STREAM_STATE_ROTATION_DATA structure
Describes stream-state data that specifies the clockwise rotation of the display output surface.

## Syntax
````
typedef struct _DXVAHDDDI_STREAM_STATE_ROTATION_DATA {
  BOOL               Enable;
  DXVAHDDDI_ROTATION Rotation;
} DXVAHDDDI_STREAM_STATE_ROTATION_DATA;
````

## Members


`Enable`

A Boolean value that specifies whether the driver should rotate the output surface. The default value is <b>FALSE</b>, which indicates that rotation is disabled.

`Rotation`

The clockwise degrees of rotation as specified by a <a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_rotation.md">DXVAHDDDI_ROTATION</a> enumeration value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h |

## See Also

<a href="..\d3dumddi\ne-d3dumddi-_dxvahdddi_rotation.md">DXVAHDDDI_ROTATION</a>