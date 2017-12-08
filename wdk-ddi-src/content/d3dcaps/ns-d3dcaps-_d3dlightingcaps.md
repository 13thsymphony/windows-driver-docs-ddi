---
UID: NS.D3DCAPS._D3DLIGHTINGCAPS
title: _D3DLIGHTINGCAPS
author: windows-driver-content
description: Obsolete in DirectX 8.0 and later versions; see Remarks. The D3DLIGHTINGCAPS structure describes the lighting capabilities of a device.
old-location: display\d3dlightingcaps.htm
old-project: display
ms.assetid: ea8ba463-e8dd-4952-bcad-6fe565fe3292
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _D3DLIGHTINGCAPS, *LPD3DLIGHTINGCAPS, D3DLIGHTINGCAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dcaps.h
req.include-header: D3dcaps.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DLIGHTINGCAPS
req.alt-loc: d3dcaps.h
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

# _D3DLIGHTINGCAPS structure



## -description

   Obsolete in DirectX 8.0 and later versions; see Remarks.
   
The D3DLIGHTINGCAPS structure describes the lighting capabilities of a device.


## -syntax

````
typedef struct _D3DLIGHTINGCAPS {
  DWORD dwSize;
  DWORD dwCaps;
  DWORD dwLightingModel;
  DWORD dwNumLights;
} D3DLIGHTINGCAPS, *LPD3DLIGHTINGCAPS;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the D3DLIGHTINGCAPS structure. 

### -field dwCaps

 Specifies flags describing the capabilities of the lighting module. The following flags are defined:   
  
  
  
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>D3DLIGHTCAPS_DIRECTIONAL</td>
<td>Directional lights are supported. 
</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_GLSPOT</td>
<td>OpenGL-style spotlights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_PARALLELPOINT</td>
<td>Parallel-point lights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_POINT</td>
<td>Point lights are supported.</td>
</tr>
<tr>
<td>D3DLIGHTCAPS_SPOT</td>
<td>Spotlights are supported. 
</td>
</tr>
</table>
 

### -field dwLightingModel

 Specifies flags indicating whether the lighting model is RGB or monochrome. The following flags are defined: 
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>D3DLIGHTINGMODEL_MONO </td>
<td>The lighting model is monochromatic. 
 </td>
</tr>
<tr>
<td>D3DLIGHTINGMODEL_RGB</td>
<td>The lighting model is RGB. 
</td>
</tr>
</table>
 

### -field dwNumLights

Specifies the number of lights that can be handled.

## -remarks
This structure has been replaced by D3DCAPS8 (see the DirectX 8.0 SDK documentation) for DirectX 8.0 and later runtimes, but is required for DirectX 7.0 and earlier runtime compatibility. See <a href="https://msdn.microsoft.com/a03a7cbc-95be-4251-8e3a-bef4a093f03d">Reporting DirectX 8.0 Style Direct3D Capabilities</a> for details.

This structure is a member of the <a href="display.d3ddevicedesc_v1">D3DDEVICEDESC_V1</a> structure.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dcaps.h (include D3dcaps.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3ddevicedesc_v1">D3DDEVICEDESC_V1</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DLIGHTINGCAPS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
