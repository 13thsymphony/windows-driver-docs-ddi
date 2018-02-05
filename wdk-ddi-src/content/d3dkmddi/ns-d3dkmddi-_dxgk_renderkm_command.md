---
UID : NS:d3dkmddi._DXGK_RENDERKM_COMMAND
title : "_DXGK_RENDERKM_COMMAND"
author : windows-driver-content
description : The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.
old-location : display\dxgk_renderkm_command.htm
old-project : display
ms.assetid : 998bf0ca-c08d-41d9-ba3e-74a620ed51ae
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3dkmddi/DXGK_RENDERKM_COMMAND, DXGK_RENDERKM_COMMAND structure [Display Devices], DXGK_RENDERKM_COMMAND, _DXGK_RENDERKM_COMMAND, display.dxgk_renderkm_command, DmStructs_b23578a5-ae81-42c8-95ce-3ba9b4691d57.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3dkmddi.h
req.include-header : D3dkmddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : DXGK_RENDERKM_COMMAND
---

# _DXGK_RENDERKM_COMMAND structure
The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.

## Syntax
````
typedef struct _DXGK_RENDERKM_COMMAND {
  DXGK_RENDERKM_OPERATION OpCode;
  UINT                    CommandSize;
  union {
    DXGK_GDIARG_BITBLT         BitBlt;
    DXGK_GDIARG_COLORFILL      ColorFill;
    DXGK_GDIARG_ALPHABLEND     AlphaBlend;
    DXGK_GDIARG_STRETCHBLT     StretchBlt;
    DXGK_GDIARG_TRANSPARENTBLT TransparentBlt;
    DXGK_GDIARG_CLEARTYPEBLEND ClearTypeBlend;
  } Command;
} DXGK_RENDERKM_COMMAND;
````

## Members


`Command`



`CommandSize`

[in] The size of the current command, in bytes. This is equal to the number of bytes from the beginning of DXGK_RENDERKM_COMMAND up to the next command.

`OpCode`

[in] A <a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_renderkm_operation.md">DXGK_RENDERKM_OPERATION</a>-type operation code that identifies the GDI hardware-accelerated rendering operation to process. For more information about GDI hardware acceleration, see the Remarks section.

## Remarks
An array of variable-size DXGK_RENDERKM_COMMAND structures defines a command buffer that is used to control GDI hardware-accelerated rendering.

A display miniport driver should report that it supports command buffer processing for GDI hardware acceleration by setting <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>-&gt;<b>PresentationCaps</b>.<b>SupportKernelModeCommandBuffer</b> to <b>TRUE</b>.
<div class="alert"><b>Note</b>    A display miniport driver should report that it supports GDI hardware acceleration only if the cache-coherent GPU aperture segment exists, and there is no significant performance penalty when the CPU accesses the memory.</div><div> </div>Each command varies in length depending on the value of the <b>OpCode</b> member and the number of sub-rectangles in the command.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of the Windows operating systems. Available in Windows 7 and later versions of the Windows operating systems. |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_bitblt.md">DXGK_GDIARG_BITBLT</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_stretchblt.md">DXGK_GDIARG_STRETCHBLT</a>

<a href="..\d3dkmddi\ne-d3dkmddi-_dxgk_renderkm_operation.md">DXGK_RENDERKM_OPERATION</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_presentationcaps.md">DXGK_PRESENTATIONCAPS</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_colorfill.md">DXGK_GDIARG_COLORFILL</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_transparentblt.md">DXGK_GDIARG_TRANSPARENTBLT</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_cleartypeblend.md">DXGK_GDIARG_CLEARTYPEBLEND</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_drivercaps.md">DXGK_DRIVERCAPS</a>

<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_gdiarg_alphablend.md">DXGK_GDIARG_ALPHABLEND</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RENDERKM_COMMAND structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>