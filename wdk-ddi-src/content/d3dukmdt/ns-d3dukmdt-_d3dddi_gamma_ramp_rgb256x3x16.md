---
UID: NS:d3dukmdt._D3DDDI_GAMMA_RAMP_RGB256x3x16
title: "_D3DDDI_GAMMA_RAMP_RGB256x3x16"
author: windows-driver-content
description: The D3DDDI_GAMMA_RAMP_RGB256x3x16 structure contains a gamma lookup table.
old-location: display\d3dddi_gamma_ramp_rgb256x3x16.htm
old-project: display
ms.assetid: d5a8a040-0b96-4eb9-b90f-f506de89559f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DmStructs_803b0bbe-a2a2-4e61-82da-11db95413949.xml, display.d3dddi_gamma_ramp_rgb256x3x16, _D3DDDI_GAMMA_RAMP_RGB256x3x16, D3DDDI_GAMMA_RAMP_RGB256x3x16, D3DDDI_GAMMA_RAMP_RGB256x3x16 structure [Display Devices], d3dukmdt/D3DDDI_GAMMA_RAMP_RGB256x3x16
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dukmdt.h
apiname:
-	D3DDDI_GAMMA_RAMP_RGB256x3x16
product: Windows
targetos: Windows
req.typenames: D3DDDI_GAMMA_RAMP_RGB256x3x16
---

# _D3DDDI_GAMMA_RAMP_RGB256x3x16 structure
The D3DDDI_GAMMA_RAMP_RGB256x3x16 structure contains a gamma lookup table.

## Syntax
````
typedef struct _D3DDDI_GAMMA_RAMP_RGB256x3x16 {
  USHORT Red[256];
  USHORT Green[256];
  USHORT Blue[256];
} D3DDDI_GAMMA_RAMP_RGB256x3x16;
````

## Members


`Blue`

An array of 16-bit values that holds the gamma function for the blue color channel.

`Green`

An array of 16-bit values that holds the gamma function for the green color channel.

`Red`

An array of 16-bit values that holds the gamma function for the red color channel.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |

## See Also

<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_gammaramp_type.md">D3DDDI_GAMMARAMP_TYPE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_GAMMA_RAMP_RGB256x3x16 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>