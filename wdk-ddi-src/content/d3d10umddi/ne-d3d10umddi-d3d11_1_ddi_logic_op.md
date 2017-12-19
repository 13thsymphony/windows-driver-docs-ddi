---
UID: NE.d3d10umddi.D3D11_1_DDI_LOGIC_OP
title: D3D11_1_DDI_LOGIC_OP
author: windows-driver-content
description: Indicates shader logic operations used in a blend state.
old-location: display\d3d11_1_ddi_logic_op.htm
old-project: display
ms.assetid: 5ea964a2-7d80-4846-bee8-a5476cc8d0fa
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D11_1_DDI_LOGIC_OP, D3D11_1_DDI_LOGIC_OP
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1_DDI_LOGIC_OP
req.alt-loc: D3d10umddi.h
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
---

# D3D11_1_DDI_LOGIC_OP enumeration



## -description
Indicates shader logic operations used in a blend state.

In the following notation, the output value of each logic operation is given in terms of these values:<dl>
<dd><i>s</i> is the pixel shader output</dd>
<dd><i>d</i> is the contents of the render target view (RTV)</dd>
</dl>




## -syntax

````
typedef enum D3D11_1_DDI_LOGIC_OP { 
  D3D11_1_DDI_LOGIC_OP_CLEAR          = 0,
  D3D11_1_DDI_LOGIC_OP_SET            = 1,
  D3D11_1_DDI_LOGIC_OP_COPY           = 2,
  D3D11_1_DDI_LOGIC_OP_COPY_INVERTED  = 3,
  D3D11_1_DDI_LOGIC_OP_NOOP           = 4,
  D3D11_1_DDI_LOGIC_OP_INVERT         = 5,
  D3D11_1_DDI_LOGIC_OP_AND            = 6,
  D3D11_1_DDI_LOGIC_OP_NAND           = 7,
  D3D11_1_DDI_LOGIC_OP_OR             = 8,
  D3D11_1_DDI_LOGIC_OP_NOR            = 9,
  D3D11_1_DDI_LOGIC_OP_XOR            = 10,
  D3D11_1_DDI_LOGIC_OP_EQUIV          = 11,
  D3D11_1_DDI_LOGIC_OP_AND_REVERSE    = 12,
  D3D11_1_DDI_LOGIC_OP_AND_INVERTED   = 13,
  D3D11_1_DDI_LOGIC_OP_OR_REVERSE     = 14,
  D3D11_1_DDI_LOGIC_OP_OR_INVERTED    = 15
} D3D11_1_DDI_LOGIC_OP;
````


## -enum-fields
<dl>
<dd><i>s</i> is the pixel shader output</dd>
<dd><i>d</i> is the contents of the render target view (RTV)</dd>
</dl>

## -remarks
The <b>D3D11_1_DDI_LOGIC_OP</b> blend state  logic operations are specified by the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a>.<b>LogicOp</b> member in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md">CreateBlendState(D3D11_1)</a> function.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createblendstate.md">CreateBlendState(D3D11_1)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_blend_desc.md">D3D11_1_DDI_BLEND_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1_DDI_LOGIC_OP enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

