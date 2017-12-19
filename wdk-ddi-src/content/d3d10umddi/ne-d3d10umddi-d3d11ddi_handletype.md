---
UID: NE.d3d10umddi.D3D11DDI_HANDLETYPE
title: D3D11DDI_HANDLETYPE
author: windows-driver-content
description: Contains values that identify handle types.
old-location: display\d3d11ddi_handletype.htm
old-project: display
ms.assetid: 9ac032fe-b870-49aa-8602-3c7aa997ef9a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D11DDI_HANDLETYPE, D3D11DDI_HANDLETYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_HANDLETYPE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11DDI_HANDLETYPE
req.alt-loc: d3d10umddi.h
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

# D3D11DDI_HANDLETYPE enumeration



## -description
Contains values that identify handle types. 



## -syntax

````
typedef enum D3D11DDI_HANDLETYPE { 
  D3D10DDI_HT_RESOURCE                           = 0,
  D3D10DDI_HT_SHADERRESOURCEVIEW                 = 1,
  D3D10DDI_HT_RENDERTARGETVIEW                   = 2,
  D3D10DDI_HT_DEPTHSTENCILVIEW                   = 3,
  D3D10DDI_HT_SHADER                             = 4,
  D3D10DDI_HT_ELEMENTLAYOUT                      = 5,
  D3D10DDI_HT_BLENDSTATE                         = 6,
  D3D10DDI_HT_DEPTHSTENCILSTATE                  = 7,
  D3D10DDI_HT_RASTERIZERSTATE                    = 8,
  D3D10DDI_HT_SAMPLERSTATE                       = 9,
  D3D10DDI_HT_QUERY                              = 10,
  D3D11DDI_HT_COMMANDLIST                        = 11,
  D3D11DDI_HT_UNORDEREDACCESSVIEW                = 12,
#if D3D11DDI_MINOR_HEADER_VERSION >= 3
  D3D11_1DDI_HT_DECODE                           = 13,
  D3D11_1DDI_HT_VIDEOPROCESSORENUM               = 14,
  D3D11_1DDI_HT_VIDEOPROCESSOR                   = 15,
  D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW           = 16,
  D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW          = 17,
  D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW         = 18,
#endif 
#if D3D12DDI_MINOR_HEADER_VERSION >= 2
      D3D12DDI_HT_COMMAND_QUEUE                  = ,
      D3D12DDI_HT_COMMAND_ALLOCATOR              = ,
      D3D12DDI_HT_PIPELINE_STATE                 = ,
      D3D12DDI_HT_COMMAND_LIST                   = ,
      D3D12DDI_HT_FENCE                          = ,
      D3D12DDI_HT_DESCRIPTOR_HEAP                = ,
      D3D12DDI_HT_HEAP                           = ,
      D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER  = 

#endif } D3D11DDI_HANDLETYPE;
````


## -enum-fields

### -field D3D10DDI_HT_RESOURCE

A resource handle. 


### -field D3D10DDI_HT_SHADERRESOURCEVIEW


      A shader-resource-view handle. 
     


### -field D3D10DDI_HT_RENDERTARGETVIEW

A render-target-view handle. 


### -field D3D10DDI_HT_DEPTHSTENCILVIEW

A depth-stencil-view handle. 


### -field D3D10DDI_HT_SHADER

A shader handle. 


### -field D3D10DDI_HT_ELEMENTLAYOUT

A value that identifies an element-layout handle. 


### -field D3D10DDI_HT_BLENDSTATE

A blend-state handle. 


### -field D3D10DDI_HT_DEPTHSTENCILSTATE

A depth-stencil-state handle. 


### -field D3D10DDI_HT_RASTERIZERSTATE

A rasterizer-state handle. 


### -field D3D10DDI_HT_SAMPLERSTATE

A sampler-state handle. 


### -field D3D10DDI_HT_QUERY

A query handle.


### -field D3D11DDI_HT_COMMANDLIST

A command-list handle. 


### -field D3D11DDI_HT_UNORDEREDACCESSVIEW

An unordered-access-view handle. 


### -field D3D11_1DDI_HT_DECODE

A video decoder handle.

Supported starting with Windows 8.


### -field D3D11_1DDI_HT_VIDEOPROCESSORENUM

A video processor enumeration handle.

Supported starting with Windows 8.


### -field D3D11_1DDI_HT_VIDEOPROCESSOR

A video processor handle.

Supported starting with Windows 8.


### -field D3D11_1DDI_HT_VIDEODECODEROUTPUTVIEW

A video decoder output-view handle.

Supported starting with Windows 8.


### -field D3D11_1DDI_HT_VIDEOPROCESSORINPUTVIEW

A video processor input-view handle.

Supported starting with Windows 8.


### -field D3D11_1DDI_HT_VIDEOPROCESSOROUTPUTVIEW

A video processor output-view handle.

Supported starting with Windows 8.


### -field     D3D12DDI_HT_COMMAND_QUEUE

Supported starting with Windows 10.


### -field     D3D12DDI_HT_COMMAND_ALLOCATOR

Supported starting with Windows 10.


### -field     D3D12DDI_HT_PIPELINE_STATE

Supported starting with Windows 10.


### -field     D3D12DDI_HT_COMMAND_LIST

Supported starting with Windows 10.


### -field     D3D12DDI_HT_FENCE

Supported starting with Windows 10.


### -field     D3D12DDI_HT_DESCRIPTOR_HEAP

Supported starting with Windows 10.


### -field     D3D12DDI_HT_HEAP

Supported starting with Windows 10.


### -field     D3D12DDI_HT_UNORDERED_ACCESS_VIEW_COUNTER

Supported starting with Windows 10.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
D3D11DDI_HANDLETYPE is supported beginning with the Windows 7 operating system. 

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