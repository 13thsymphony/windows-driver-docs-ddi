---
UID: NS:d3dkmthk._D3DKMT_GETDEVICESTATE
title: "_D3DKMT_GETDEVICESTATE"
author: windows-driver-content
description: The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device.
old-location: display\d3dkmt_getdevicestate.htm
old-project: display
ms.assetid: b90f8b63-51d3-4de4-9d8b-91926150fd30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_GETDEVICESTATE, D3DKMT_GETDEVICESTATE structure [Display Devices], OpenGL_Structs_39a99244-3951-4a2f-a92d-4aec50589cde.xml, _D3DKMT_GETDEVICESTATE, d3dkmthk/D3DKMT_GETDEVICESTATE, display.d3dkmt_getdevicestate
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
-	D3DKMT_GETDEVICESTATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_GETDEVICESTATE
---

# _D3DKMT_GETDEVICESTATE structure
The D3DKMT_GETDEVICESTATE structure describes parameters for retrieving the state of a device.

## Syntax
````
typedef struct _D3DKMT_GETDEVICESTATE {
  D3DKMT_HANDLE           hDevice;
  D3DKMT_DEVICESTATE_TYPE StateType;
  union {
    D3DKMT_DEVICEEXECUTION_STATE ExecutionState;
    D3DKMT_DEVICEPRESENT_STATE   PresentState;
    D3DKMT_DEVICERESET_STATE     ResetState;
  };
} D3DKMT_GETDEVICESTATE;
````

## Members


`hDevice`

[in] A handle to the device that status is requested for.

`StateType`

[in] A <a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_devicestate_type.md">D3DKMT_DEVICESTATE_TYPE</a>-typed value that indicates the type of status to retrieve for the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdevicestate.md">D3DKMTGetDeviceState</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_deviceexecution_state.md">D3DKMT_DEVICEEXECUTION_STATE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_devicepresent_state.md">D3DKMT_DEVICEPRESENT_STATE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_devicereset_state.md">D3DKMT_DEVICERESET_STATE</a>



<a href="..\d3dkmthk\ne-d3dkmthk-_d3dkmt_devicestate_type.md">D3DKMT_DEVICESTATE_TYPE</a>