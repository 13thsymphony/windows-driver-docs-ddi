---
UID: NS.D3DUKMDT._D3DDDI_HDR_METADATA_HDR10
title: _D3DDDI_HDR_METADATA_HDR10
author: windows-driver-content
description: Describes the metadata for HDR10.
old-location: display\d3dddi_hdr_metadata_hdr10.htm
old-project: display
ms.assetid: F7316327-C860-4138-A19B-3326CE9210C0
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDI_HDR_METADATA_HDR10, D3DDDI_HDR_METADATA_HDR10
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_HDR_METADATA_HDR10
req.alt-loc: d3dukmdt.h
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

# _D3DDDI_HDR_METADATA_HDR10 structure



## -description
Describes the metadata for HDR10.



## -syntax

````
typedef struct _D3DDDI_HDR_METADATA_HDR10 {
  UINT16 RedPrimary[2];
  UINT16 GreenPrimary[2];
  UINT16 BluePrimary[2];
  UINT   MaxMasteringLuminance;
  UINT   MinMasteringLuminance;
  UINT16 MaxContentLightLevel;
  UINT16 MaxFrameAverageLightLevel;
} D3DDDI_HDR_METADATA_HDR10;
````


## -struct-fields

### -field RedPrimary

The chromaticity coordinates of the 1.0 red value. Index 0 contains the X coordinate and index 1 contains the Y coordinate. 


### -field GreenPrimary

The chromaticity coordinates of the 1.0 green value. Index 0 contains the X coordinate and index 1 contains the Y coordinate. 


### -field BluePrimary

The chromaticity coordinates of the 1.0 blue value. Index 0 contains the X coordinate and index 1 contains the Y coordinate. 


### -field MaxMasteringLuminance

The maximum number of nits of the display used to master the content. 


### -field MinMasteringLuminance

The minimum number of nits of the display used to master the content.


### -field MaxContentLightLevel

The maximum nit value used anywhere in the content. 


### -field MaxFrameAverageLightLevel

The per-frame average of the maximum nit values. 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h</dt>
</dl>
</td>
</tr>
</table>