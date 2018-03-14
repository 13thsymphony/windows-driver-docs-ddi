---
UID: NS:d3dumddi._DXVADDI_PVP_BLOCK128
title: "_DXVADDI_PVP_BLOCK128"
author: windows-driver-content
description: The DXVADDI_PVP_KEY128 structure contains a 128-bit key that the decode device uses to start decoding a frame.
old-location: display\dxvaddi_pvp_key128.htm
old-project: display
ms.assetid: c4c65d1f-2531-4804-8a86-160b1ddfd692
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA2_Structs_1384e44e-aa25-470a-93bb-3e20b5885bdb.xml, DXVADDI_PVP_BLOCK128, DXVADDI_PVP_BLOCK128 structure [Display Devices], DXVADDI_PVP_KEY128, DXVADDI_PVP_KEY128 structure [Display Devices], _DXVADDI_PVP_BLOCK128, d3dumddi/DXVADDI_PVP_KEY128, display.dxvaddi_pvp_key128
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
-	DXVADDI_PVP_BLOCK128
product: Windows
targetos: Windows
req.typenames: DXVADDI_PVP_BLOCK128, DXVADDI_PVP_KEY128
---

# _DXVADDI_PVP_BLOCK128 structure
The DXVADDI_PVP_KEY128 structure contains a 128-bit key that the decode device uses to start decoding a frame.

## Syntax
````
typedef struct _DXVADDI_PVP_BLOCK128 {
  BYTE Data[16];
} DXVADDI_PVP_BLOCK128, DXVADDI_PVP_KEY128;
````

## Members


`Data`

[in] An array of 16 bytes that describes the 128-bit key that is used to start decoding.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_decodebeginframe.md">D3DDDIARG_DECODEBEGINFRAME</a>



<a href="..\d3dumddi\ns-d3dumddi-_dxvaddi_pvp_setkey.md">DXVADDI_PVP_SETKEY</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_decodebeginframe.md">DecodeBeginFrame</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_PVP_KEY128 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>