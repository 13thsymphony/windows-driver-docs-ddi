---
UID: NS:d3dkmthk._D3DKMT_DEVICEPRESENT_STATE
title: "_D3DKMT_DEVICEPRESENT_STATE"
author: windows-driver-content
description: The D3DKMT_DEVICEPRESENT_STATE structure describes parameters for retrieving the present status for a device.
old-location: display\d3dkmt_devicepresent_state.htm
old-project: display
ms.assetid: eed64347-fa5a-4b80-a28d-9190ae30b169
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_DEVICEPRESENT_STATE, D3DKMT_DEVICEPRESENT_STATE structure [Display Devices], OpenGL_Structs_d1f2fcff-dfb8-411f-a4f8-4016924b4ebd.xml, _D3DKMT_DEVICEPRESENT_STATE, d3dkmthk/D3DKMT_DEVICEPRESENT_STATE, display.d3dkmt_devicepresent_state
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
-	D3DKMT_DEVICEPRESENT_STATE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DEVICEPRESENT_STATE
---

# _D3DKMT_DEVICEPRESENT_STATE structure
The D3DKMT_DEVICEPRESENT_STATE structure describes parameters for retrieving the present status for a device.

## Syntax
````
typedef struct _D3DKMT_DEVICEPRESENT_STATE {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DKMT_PRESENT_STATS           PresentStats;
} D3DKMT_DEVICEPRESENT_STATE;
````

## Members


`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology to receive present status for.

`PresentStats`

[out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present_stats.md">D3DKMT_PRESENT_STATS</a> structure that describes status of present operations that is retrieved for the device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdevicestate.md">D3DKMT_GETDEVICESTATE</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_present_stats.md">D3DKMT_PRESENT_STATS</a>