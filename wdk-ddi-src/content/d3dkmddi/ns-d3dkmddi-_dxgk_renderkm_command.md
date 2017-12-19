---
UID: NS.D3DKMDDI._DXGK_RENDERKM_COMMAND
title: _DXGK_RENDERKM_COMMAND
author: windows-driver-content
description: The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.
old-location: display\dxgk_renderkm_command.htm
old-project: display
ms.assetid: 998bf0ca-c08d-41d9-ba3e-74a620ed51ae
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_RENDERKM_COMMAND, DXGK_RENDERKM_COMMAND
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_RENDERKM_COMMAND
req.alt-loc: d3dkmddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGK_RENDERKM_COMMAND structure



## -description
The DXGK_RENDERKM_COMMAND structure is used to construct a command buffer to control GDI hardware-accelerated rendering.



## -syntax

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


## -struct-fields

### -field OpCode


      [in] A <a href="display.dxgk_renderkm_operation">DXGK_RENDERKM_OPERATION</a>-type operation code that identifies the GDI hardware-accelerated rendering operation to process. For more information about GDI hardware acceleration, see the Remarks section.
     


### -field CommandSize


      [in] The size of the current command, in bytes. This is equal to the number of bytes from the beginning of DXGK_RENDERKM_COMMAND up to the next command.
     


### -field Command


### -field BitBlt


       [in] A bit-block transfer (bitblt) that is described by a <a href="display.dxgk_gdiarg_bitblt">DXGK_GDIARG_BITBLT</a> structure.
      


### -field ColorFill


       [in] A color fill that is described by a <a href="display.dxgk_gdiarg_colorfill">DXGK_GDIARG_COLORFILL</a> structure.
      


### -field AlphaBlend


       [in] An alpha blend that is described by a <a href="display.dxgk_gdiarg_alphablend">DXGK_GDIARG_ALPHABLEND</a> structure.
      


### -field StretchBlt


       [in] A stretch bit-block transfer that is described by a <a href="display.dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a> structure.
      


### -field TransparentBlt


       [in] A transparent bit-block transfer that is described by a <a href="display.dxgk_gdiarg_transparentblt">DXGK_GDIARG_TRANSPARENTBLT</a> structure.
      


### -field ClearTypeBlend


       [in] A ClearType blend that is described by a <a href="display.dxgk_gdiarg_cleartypeblend">DXGK_GDIARG_CLEARTYPEBLEND</a> structure.
      

</dd>
</dl>

## -remarks
An array of variable-size DXGK_RENDERKM_COMMAND structures defines a command buffer that is used to control GDI hardware-accelerated rendering.

A display miniport driver should report that it supports command buffer processing for GDI hardware acceleration by setting <a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a>-&gt;<b>PresentationCaps</b>.<b>SupportKernelModeCommandBuffer</b> to <b>TRUE</b>.

Each command varies in length depending on the value of the <b>OpCode</b> member and the number of sub-rectangles in the command.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_drivercaps">DXGK_DRIVERCAPS</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_alphablend">DXGK_GDIARG_ALPHABLEND</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_bitblt">DXGK_GDIARG_BITBLT</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_cleartypeblend">DXGK_GDIARG_CLEARTYPEBLEND</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_colorfill">DXGK_GDIARG_COLORFILL</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_stretchblt">DXGK_GDIARG_STRETCHBLT</a>
</dt>
<dt>
<a href="display.dxgk_gdiarg_transparentblt">DXGK_GDIARG_TRANSPARENTBLT</a>
</dt>
<dt>
<a href="display.dxgk_presentationcaps">DXGK_PRESENTATIONCAPS</a>
</dt>
<dt>
<a href="display.dxgk_renderkm_operation">DXGK_RENDERKM_OPERATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_RENDERKM_COMMAND structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

