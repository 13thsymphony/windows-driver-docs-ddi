---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
title: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
author: windows-driver-content
description: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG describes the type of context being created for interacting with JPEG hardware.
old-location: display\d3dwddm2_0ddi_contexttype_flag.htm
old-project: display
ms.assetid: F767C051-637A-4912-80B0-36C4DF7E46DD
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG, D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
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
req.typenames: D3DWDDM2_0DDI_CONTEXTTYPE_FLAG
---

# D3DWDDM2_0DDI_CONTEXTTYPE_FLAG enumeration



## -description
<b>D3DWDDM2_0DDI_CONTEXTTYPE_FLAG</b> describes the type of context being created for interacting with JPEG hardware.



## -syntax

````
typedef enum _D3DWDDM2_0DDI_CONTEXTTYPE_FLAG { 
  D3DWDDM2_0DDI_CONTEXTTYPE_ALL      = 0x00000000,
  D3DWDDM2_0DDI_CONTEXTTYPE_3D       = 0x00000001,
  D3DWDDM2_0DDI_CONTEXTTYPE_COMPUTE  = 0x00000002,
  D3DWDDM2_0DDI_CONTEXTTYPE_COPY     = 0x00000004,
  D3DWDDM2_0DDI_CONTEXTTYPE_VIDEO    = 0x00000008,
  D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE    = 0x00000010
} D3DWDDM2_0DDI_CONTEXTTYPE_FLAG;
````


## -enum-fields

### -field D3DWDDM2_0DDI_CONTEXTTYPE_ALL

Indicates that all JPEG contexts should be created.


### -field D3DWDDM2_0DDI_CONTEXTTYPE_3D

Indicates that a JPEG 3D context should be created.


### -field D3DWDDM2_0DDI_CONTEXTTYPE_COMPUTE

Indicates that a JPEG compute context should be created.


### -field D3DWDDM2_0DDI_CONTEXTTYPE_COPY

Indicates that  a JPEG copy context should be created.


### -field D3DWDDM2_0DDI_CONTEXTTYPE_VIDEO

Indicates that a JPEG video context should be created.


### -field D3DWDDM2_0DDI_CONTEXTTYPE_IMAGE

Indicates that a JPEG image context should be created.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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