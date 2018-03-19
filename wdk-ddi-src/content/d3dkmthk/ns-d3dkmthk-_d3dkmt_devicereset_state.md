---
UID: NS:d3dkmthk._D3DKMT_DEVICERESET_STATE
title: "_D3DKMT_DEVICERESET_STATE"
author: windows-driver-content
description: The D3DKMT_DEVICERESET_STATE structure identifies reset status.
old-location: display\d3dkmt_devicereset_state.htm
old-project: display
ms.assetid: c2037d77-8745-4307-ac12-54f62f20c2d9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_DEVICERESET_STATE, D3DKMT_DEVICERESET_STATE structure [Display Devices], OpenGL_Structs_03e42382-c472-4f0b-9183-a1b6630f64cf.xml, _D3DKMT_DEVICERESET_STATE, d3dkmthk/D3DKMT_DEVICERESET_STATE, display.d3dkmt_devicereset_state
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	d3dkmthk.h
api_name:
-	D3DKMT_DEVICERESET_STATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICERESET_STATE
---

# _D3DKMT_DEVICERESET_STATE structure
The D3DKMT_DEVICERESET_STATE structure identifies reset status.

## Syntax
````
typedef struct _D3DKMT_DEVICERESET_STATE {
  union {
    struct {
      UINT DesktopSwitched  :1;
      UINT Reserved  :31;
    };
    UINT   Value;
  };
} D3DKMT_DEVICERESET_STATE;
````

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>