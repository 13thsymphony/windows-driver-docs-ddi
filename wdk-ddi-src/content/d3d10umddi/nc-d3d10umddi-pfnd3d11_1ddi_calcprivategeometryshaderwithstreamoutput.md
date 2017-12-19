---
UID: NC.d3d10umddi.PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.
old-location: display\calcprivategeometryshaderwithstreamoutput_d3d11_1_.htm
old-project: display
ms.assetid: 316e30b9-eb06-483c-a124-476b4308cf5f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)
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

# PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback



## -description
Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.



## -prototype

````
PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT CalcPrivateGeometryShaderWithStreamOutput(D3D11_1);

SIZE_T APIENTRY* CalcPrivateGeometryShaderWithStreamOutput(D3D11_1)(
             D3D10DDI_HDEVICE                                 hDevice,
  _In_ const D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT *pOutput,
  _In_ const D3D11_1DDIARG_STAGE_IO_SIGNATURES                *pSignatures
)
{ ... }
````


## -parameters

### -param hDevice 

 A handle to the display device (graphics context).


### -param pOutput [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_creategeometryshaderwithstreamoutput.md">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a> structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.


### -param pSignatures [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a> structure that forms the shader's signature.


## -returns
The size of the memory region that the driver requires to create a geometry shader with stream output.


## -remarks


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
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_stage_io_signatures.md">D3D11_1DDIARG_STAGE_IO_SIGNATURES</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_creategeometryshaderwithstreamoutput.md">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

