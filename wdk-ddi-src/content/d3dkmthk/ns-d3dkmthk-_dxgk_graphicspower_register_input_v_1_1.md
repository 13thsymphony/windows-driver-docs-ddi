---
UID: NS:d3dkmthk._DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1
title: "_DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1"
author: windows-driver-content
description: Used to register the power state of a new input.
old-location: display\dxgk-graphicspower-register-input-v-1-1.htm
old-project: display
ms.assetid: 5b120f3c-43d2-447a-9959-0788d7decf50
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure [Display Devices], PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, display.dxgk-graphicspower-register-input-v-1-1, d3dkmthk/PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT, _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure pointer [Display Devices], d3dkmthk/DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, DXGK_GRAPHICSPOWER_REGISTER_INPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
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
-	d3dkmthk.h
apiname:
-	DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1
product: Windows
targetos: Windows
req.typenames: "*PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1"
---

# _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 structure
Used to register the power state of a new input.

## Syntax
````
typedef struct _DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1 {
  ULONG                      Version;
  PVOID                      PrivateHandle;
  PDXGK_POWER_NOTIFICATION   PowerNotificationCb;
  PDXGK_REMOVAL_NOTIFICATION RemovalNotificationCb;
  PDXGK_FSTATE_NOTIFICATION  FStateNotificationCb;
} DXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1, *PDXGK_GRAPHICSPOWER_REGISTER_INPUT_V_1_1;
````

## Members


`FStateNotificationCb`

Issues a state notification.

`PowerNotificationCb`

Issues a power notification.

`PrivateHandle`

A private handle to the device.

`RemovalNotificationCb`

Issues a removal notification.

`Version`

The current version being used.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmthk.h |