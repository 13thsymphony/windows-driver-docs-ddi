---
UID: NE:d3d10umddi.D3D11DDI_3DPIPELINELEVEL
title: D3D11DDI_3DPIPELINELEVEL
author: windows-driver-content
description: The D3D11DDI_3DPIPELINELEVEL enumeration type contains values that identify the pipeline level that the driver supports, which is retrieved from a call to the driver's GetCaps(D3D10_2) function.
old-location: display\d3d11ddi_3dpipelinelevel.htm
old-project: display
ms.assetid: 824008f2-fe83-47ea-9387-38978b98e7e4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11DDI_3DPIPELINELEVEL, D3D11DDI_3DPIPELINELEVEL enumeration [Display Devices], D3D11DDI_3DPIPELINELEVEL_10_0, D3D11DDI_3DPIPELINELEVEL_10_1, D3D11DDI_3DPIPELINELEVEL_11_0, D3D11_1DDI_3DPIPELINELEVEL_11_1, D3D11_1DDI_3DPIPELINELEVEL_9_1, D3D11_1DDI_3DPIPELINELEVEL_9_2, D3D11_1DDI_3DPIPELINELEVEL_9_3, UMDisplayDriver_Dx11param_Structs_194835cf-19d6-43d1-9c4d-726a06c0a4cb.xml, d3d10umddi/D3D11DDI_3DPIPELINELEVEL, d3d10umddi/D3D11DDI_3DPIPELINELEVEL_10_0, d3d10umddi/D3D11DDI_3DPIPELINELEVEL_10_1, d3d10umddi/D3D11DDI_3DPIPELINELEVEL_11_0, d3d10umddi/D3D11_1DDI_3DPIPELINELEVEL_11_1, d3d10umddi/D3D11_1DDI_3DPIPELINELEVEL_9_1, d3d10umddi/D3D11_1DDI_3DPIPELINELEVEL_9_2, d3d10umddi/D3D11_1DDI_3DPIPELINELEVEL_9_3, display.d3d11ddi_3dpipelinelevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_3DPIPELINELEVEL is supported beginning with the Windows 7 operating system.
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
-	D3D11DDI_3DPIPELINELEVEL
product: Windows
targetos: Windows
req.typenames: D3D11DDI_3DPIPELINELEVEL
---

# D3D11DDI_3DPIPELINELEVEL Enumeration
The D3D11DDI_3DPIPELINELEVEL enumeration type contains values that identify the pipeline level that the driver supports, which is retrieved from a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

## Syntax
````
typedef enum D3D11DDI_3DPIPELINELEVEL { 
  D3D11DDI_3DPIPELINELEVEL_10_0    = 0,
  D3D11DDI_3DPIPELINELEVEL_10_1    = 1,
  D3D11DDI_3DPIPELINELEVEL_11_0    = 2,
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDI_3DPIPELINELEVEL_11_1  = 3,
  D3D11_1DDI_3DPIPELINELEVEL_9_1   = 4,
  D3D11_1DDI_3DPIPELINELEVEL_9_2   = 5,
  D3D11_1DDI_3DPIPELINELEVEL_9_3   = 6

#endif } D3D11DDI_3DPIPELINELEVEL;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11DDI_3DPIPELINELEVEL_10_0</td>
                    <td>The driver supports Direct3D version 10 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11DDI_3DPIPELINELEVEL_10_1</td>
                    <td>The driver supports Direct3D version 10.1 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11DDI_3DPIPELINELEVEL_11_0</td>
                    <td>The driver supports Direct3D version 11 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_3DPIPELINELEVEL_11_1</td>
                    <td>Supported beginning with Windows 8.

The driver supports Direct3D version 11.1 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_3DPIPELINELEVEL_9_1</td>
                    <td>Supported beginning with Windows 8.

The driver supports Direct3D version 9.1 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_3DPIPELINELEVEL_9_2</td>
                    <td>Supported beginning with Windows 8.

The driver supports Direct3D version 9.2 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3D11_1DDI_3DPIPELINELEVEL_9_3</td>
                    <td>Supported beginning with Windows 8.

The driver supports Direct3D version 9.3 pipeline.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_3DPIPELINELEVEL_12_0</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_3DPIPELINELEVEL_12_1</td>
                    <td></td>
                </tr>
</table>

## Remarks

The driver uses one of the values from the D3D11DDI_3DPIPELINELEVEL enumeration and the following macro to encode the 3-D pipeline level:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define D3D11DDI_ENCODE_3DPIPELINESUPPORT_CAP( Level ) (0x1 &lt;&lt; Level)</pre>
</td>
</tr>
</table></span></div>
The driver then uses the macro's result in the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a> structure to provide information to the Direct3D runtime when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function with the <b>Type</b> member of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddiarg_getcaps.md">D3D10_2DDIARG_GETCAPS</a> set to D3D11DDICAPS_3DPIPELINESUPPORT.

The driver uses the following constant and macros to extract one of the values from the D3D11DDI_3DPIPELINELEVEL enumeration that represents the 3-D pipeline level to set for a display device. The driver extracts the value from the <b>Caps</b> member of D3D11DDI_3DPIPELINESUPPORT_CAPS. The driver uses the 3-D pipeline level to create the appropriate display device when the driver receives a call to its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT (0x1)
#define D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK (0x7 &lt;&lt; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT)
#define D3D11DDI_EXTRACT_3DPIPELINELEVEL_FROM_FLAGS( Flags ) \
    ((D3D11DDI_3DPIPELINELEVEL)(((Flags) &amp; D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_MASK) &gt;&gt; \
    D3D11DDI_CREATEDEVICE_FLAG_3DPIPELINESUPPORT_SHIFT))</pre>
</td>
</tr>
</table></span></div>
For more information about the Direct3D version 10 pipeline, see <a href="https://msdn.microsoft.com/63672d6e-5c5d-4873-a104-991e0b17d128">Rendering Pipeline</a>. 

For more information about the Direct3D version 11 pipelines, see <a href="https://msdn.microsoft.com/7d724751-761e-409c-8398-d1b5d58c057c">Pipelines for Direct3D Version 11</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11DDI_3DPIPELINELEVEL is supported beginning with the Windows 7 operating system. D3D11DDI_3DPIPELINELEVEL is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_2ddiarg_getcaps.md">D3D10_2DDIARG_GETCAPS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_3dpipelinesupport_caps.md">D3D11DDI_3DPIPELINESUPPORT_CAPS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>