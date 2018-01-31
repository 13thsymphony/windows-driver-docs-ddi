---
UID : NE:d3d10umddi.D3D10_DDI_RESOURCE_BIND_FLAG
title : D3D10_DDI_RESOURCE_BIND_FLAG
author : windows-driver-content
description : Identifies how a resource is bound.
old-location : display\d3d10_ddi_resource_bind_flag.htm
old-project : display
ms.assetid : 1c911435-5a55-4b92-9c65-3116d98f8ecf
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3d10umddi/D3D11_DDI_BIND_MASK, D3D10_DDI_BIND_STREAM_OUTPUT, d3d10umddi/D3D10_DDI_BIND_PIPELINE_MASK, d3d10umddi/D3D10_DDI_BIND_PRESENT, D3D10_DDI_BIND_PRESENT, d3d10umddi/D3D10_DDI_BIND_RENDER_TARGET, D3D11_DDI_BIND_PIPELINE_MASK, d3d10umddi/D3D10_DDI_BIND_DEPTH_STENCIL, D3D10_DDI_BIND_CONSTANT_BUFFER, D3D11_DDI_BIND_DECODER, D3D11_DDI_BIND_MASK, d3d10umddi/D3D11_DDI_BIND_DECODER, d3d10umddi/D3D11_DDI_BIND_PIPELINE_MASK, D3D11_DDI_BIND_VIDEO_ENCODER, D3D10_DDI_RESOURCE_BIND_FLAG enumeration [Display Devices], d3d10umddi/D3D10_DDI_BIND_VERTEX_BUFFER, D3D10_DDI_BIND_SHADER_RESOURCE, D3D10_DDI_BIND_INDEX_BUFFER, d3d10umddi/D3D10_DDI_BIND_STREAM_OUTPUT, D3D10_DDI_BIND_DEPTH_STENCIL, d3d10umddi/D3D10_DDI_BIND_CONSTANT_BUFFER, d3d10umddi/D3D10_DDI_BIND_INDEX_BUFFER, D3D10_DDI_BIND_VERTEX_BUFFER, D3D10_DDI_BIND_MASK, UMDisplayDriver_Dx10param_Structs_bb674d0e-4e3d-42ce-9216-2937f466b1f5.xml, d3d10umddi/D3D11_DDI_BIND_UNORDERED_ACCESS, d3d10umddi/D3D11_DDI_BIND_CAPTURE, d3d10umddi/D3D10_DDI_BIND_MASK, D3D11_DDI_BIND_CAPTURE, D3D10_DDI_BIND_PIPELINE_MASK, d3d10umddi/D3D10_DDI_RESOURCE_BIND_FLAG, D3D10_DDI_BIND_RENDER_TARGET, d3d10umddi/D3D10_DDI_BIND_SHADER_RESOURCE, D3D10_DDI_RESOURCE_BIND_FLAG, display.d3d10_ddi_resource_bind_flag, d3d10umddi/D3D11_DDI_BIND_VIDEO_ENCODER, D3D11_DDI_BIND_UNORDERED_ACCESS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D10_DDI_RESOURCE_BIND_FLAG
---

# D3D10_DDI_RESOURCE_BIND_FLAG Enumeration
Identifies how a resource is bound.

## Syntax
````
typedef enum D3D10_DDI_RESOURCE_BIND_FLAG { 
  D3D10_DDI_BIND_VERTEX_BUFFER     = 0x00000001L,
  D3D10_DDI_BIND_INDEX_BUFFER      = 0x00000002L,
  D3D10_DDI_BIND_CONSTANT_BUFFER   = 0x00000004L,
  D3D10_DDI_BIND_SHADER_RESOURCE   = 0x00000008L,
  D3D10_DDI_BIND_STREAM_OUTPUT     = 0x00000010L,
  D3D10_DDI_BIND_RENDER_TARGET     = 0x00000020L,
  D3D10_DDI_BIND_DEPTH_STENCIL     = 0x00000040L,
  D3D10_DDI_BIND_PIPELINE_MASK     = 0x0000007FL,
  D3D10_DDI_BIND_PRESENT           = 0x00000080L,
  D3D10_DDI_BIND_MASK              = 0x000000FFL,
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_DDI_BIND_UNORDERED_ACCESS  = 0x00000100L,
  D3D11_DDI_BIND_DECODER           = 0x00000200L,
  D3D11_DDI_BIND_VIDEO_ENCODER     = 0x00000400L,
  D3D11_DDI_BIND_CAPTURE           = 0x00000800L,
  D3D11_DDI_BIND_PIPELINE_MASK     = 0x00000F7FL,
  D3D11_DDI_BIND_MASK              = 0x00000FFFL,
#else 
#if D3D11DDI_MINOR_HEADER_VERSION >= 1
  D3D11_DDI_BIND_UNORDERED_ACCESS  = 0x00000100L,
  D3D11_DDI_BIND_PIPELINE_MASK     = 0x0000017FL,
  D3D11_DDI_BIND_MASK              = 0x000001FFL
#endif 

#endif } D3D10_DDI_RESOURCE_BIND_FLAG;
````

## Constants

<table>

<tr>
<td>D3D10_DDI_BIND_CONSTANT_BUFFER</td>
<td>The resource can be bound as a constant buffer.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_DEPTH_STENCIL</td>
<td>The resource can be bound as a depth-stencil buffer.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_INDEX_BUFFER</td>
<td>The resource can be bound as an index buffer in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a> function.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_MASK</td>
<td>A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 10 values from this enumeration.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_PIPELINE_MASK</td>
<td>A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first seven values from this enumeration.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_PRESENT</td>
<td>The resource can be used in a call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a> function (that is, the resource can be used as a back buffer).</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_RENDER_TARGET</td>
<td>The resource can be bound as a render target.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_SHADER_RESOURCE</td>
<td>The resource can be bound as a shader resource in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a>, <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a>, or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a> function.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_STREAM_OUTPUT</td>
<td>The resource can be bound as a stream output.</td>
</tr>

<tr>
<td>D3D10_DDI_BIND_VERTEX_BUFFER</td>
<td>The resource can be bound as a vertex buffer in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md">IaSetVertexBuffers</a> function.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_CAPTURE</td>
<td>The 2-D texture is used to receive data from the capture interface.

This value cannot be used simultaneously with these values from this enumeration:<ul>
<li><b>D3D11_DDI_BIND_CONSTANT_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_DECODER</b></li>
<li><b>D3D11_DDI_BIND_DEPTH_STENCIL</b></li>
<li><b>D3D11_DDI_BIND_INDEX_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_RENDER_TARGET</b></li>
<li><b>D3D11_DDI_BIND_STREAM_OUTPUT</b></li>
<li><b>D3D11_DDI_BIND_UNORDERED_ACCESS</b></li>
<li><b>D3D11_DDI_BIND_VERTEX_BUFFER</b></li>
</ul>


Supported starting with Windows 8.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_DECODER</td>
<td>The resource is a two-dimensional (2-D) texture that is filled by the video decoder engine.

This value cannot be used simultaneously with the <b>D3D10_DDI_BIND_RENDER_TARGET</b> enumeration value.

Supported starting with Windows 8.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_MASK</td>
<td>A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 11 and version 10 values from this enumeration.

Supported starting with Windows 8.

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the Direct3D version 11 and version 10 values from this enumeration.

Supported starting with Windows 7.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_PIPELINE_MASK</td>
<td>A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first nine values from this enumeration.

Supported starting with Windows 8.

A mask value that indicates the valid bitfields in a bitwise <b>OR</b> combination of the first nine values from this enumeration.

Supported starting with Windows 7.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_UNORDERED_ACCESS</td>
<td>The resource can be bound as an unordered-access buffer.

Supported starting with Windows 8.

The resource can be bound as an unordered-access buffer.

Supported starting with Windows 7.</td>
</tr>

<tr>
<td>D3D11_DDI_BIND_VIDEO_ENCODER</td>
<td>The resource is used as an input for a hardware-encode Media Foundation Transform (MFT).

This value cannot be used simultaneously with these values from this enumeration:<ul>
<li><b>D3D11_DDI_BIND_CONSTANT_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_DEPTH_STENCIL</b></li>
<li><b>D3D11_DDI_BIND_INDEX_BUFFER</b></li>
<li><b>D3D11_DDI_BIND_VERTEX_BUFFER</b></li>
</ul>


Supported starting with Windows 8.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setindexbuffer.md">IaSetIndexBuffer</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">VsSetShaderResources</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">GsSetShaderResources</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569179">PresentDXGI</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setshaderresources.md">PsSetShaderResources</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_ia_setvertexbuffers.md">IaSetVertexBuffers</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_RESOURCE_BIND_FLAG enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>