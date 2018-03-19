---
UID: NS:d3dumddi._DXVADDI_PVP_HW_IV
title: "_DXVADDI_PVP_HW_IV"
author: windows-driver-content
description: The DXVADDI_PVP_HW_IV structure contains two 64-bit values that combine to form a 128-bit protected video path (PVP) value.
old-location: display\dxvaddi_pvp_hw_iv.htm
old-project: display
ms.assetid: 8ba29a38-1bf9-47a9-8da6-1f92eb8e8733
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_c4bb4df0-ed9d-494e-84ff-fcd8e68aac36.xml, DXVADDI_PVP_HW_IV, DXVADDI_PVP_HW_IV structure [Display Devices], _DXVADDI_PVP_HW_IV, d3dumddi/DXVADDI_PVP_HW_IV, display.dxvaddi_pvp_hw_iv
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DXVADDI_PVP_HW_IV
product: Windows
targetos: Windows
req.typenames: DXVADDI_PVP_HW_IV
---

# _DXVADDI_PVP_HW_IV structure
The DXVADDI_PVP_HW_IV structure contains two 64-bit values that combine to form a 128-bit protected video path (PVP) value.

## Syntax
````
typedef struct _DXVADDI_PVP_HW_IV {
  ULONGLONG IV;
  ULONGLONG Count;
} DXVADDI_PVP_HW_IV;
````

## Members


`IV`

[in] A 64-bit initialization vector.

`Count`

[in] A 64-bit number.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_decodebufferdesc.md">DXVADDI_DECODEBUFFERDESC</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodeexecute.md">DecodeExecute</a>