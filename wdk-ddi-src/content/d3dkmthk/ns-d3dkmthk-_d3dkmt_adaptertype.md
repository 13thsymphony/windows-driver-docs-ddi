---
UID: NS.D3DKMTHK._D3DKMT_ADAPTERTYPE
title: _D3DKMT_ADAPTERTYPE
author: windows-driver-content
description: Specifies the type of display device that the graphics adapter supports.
old-location: display\d3dkmt_adaptertype.htm
old-project: display
ms.assetid: a92865bc-620f-434d-a185-b837924599fc
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DKMT_ADAPTERTYPE, D3DKMT_ADAPTERTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMT_ADAPTERTYPE
req.alt-loc: D3dkmthk.h
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

# _D3DKMT_ADAPTERTYPE structure



## -description
Specifies the type of display device that the graphics adapter supports.



## -syntax

````
typedef struct _D3DKMT_ADAPTERTYPE {
  UINT RenderSupported  :1;
  UINT DisplaySupported  :1;
  UINT SoftwareDevice  :1;
  UINT PostDevice  :1;
  UINT Reserved  :28;
} D3DKMT_ADAPTERTYPE;
````


## -struct-fields

### -field RenderSupported

The adapter supports a render device.


### -field DisplaySupported

The adapter supports a display device.


### -field SoftwareDevice

The adapter supports a non-plug and play (PnP) device that is implemented in software.


### -field PostDevice

The adapter supports a power-on self-test (POST) device.


### -field Reserved

Reserved for system use.


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
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
</table>