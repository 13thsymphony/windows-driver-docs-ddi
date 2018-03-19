---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.
old-location: display\d3d10ddiarg_creategeometryshaderwithstreamoutput.htm
old-project: display
ms.assetid: 172af07e-9cc7-48d1-900a-93f18bdc37a9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_c41e18d8-8aca-4902-b921-0916f3ca2042.xml, d3d10umddi/D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, display.d3d10ddiarg_creategeometryshaderwithstreamoutput
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
---

# D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure
The D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT structure describes the geometry shader with stream output to create.

## Syntax
````
typedef struct D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT {
  const UINT                                        *pShaderCode;
  const D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY *pOutputStreamDecl;
  UINT                                              NumEntries;
  UINT                                              StreamOutputStrideInBytes;
} D3D10DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT;
````

## Members


`pShaderCode`

[in] An array of CONST UINT tokens that make up the geometry shader code.

`pOutputStreamDecl`

[in] An array of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry.md">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a> structures that describes the stream output for the geometry shader.

`NumEntries`

[in] The number of elements in that array that the <b>pOutputStreamDecl</b> member specifies.

`StreamOutputStrideInBytes`

[in] The size, in bytes, from one vertex to the next vertex.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_stream_output_declaration_entry.md">D3D10DDIARG_STREAM_OUTPUT_DECLARATION_ENTRY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_creategeometryshaderwithstreamoutput.md">CreateGeometryShaderWithStreamOutput</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivategeometryshaderwithstreamoutput.md">CalcPrivateGeometryShaderWithStreamOutput</a>