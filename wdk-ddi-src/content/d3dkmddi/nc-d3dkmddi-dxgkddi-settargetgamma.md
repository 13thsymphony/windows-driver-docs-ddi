---
UID: NC.d3dkmddi.DXGKDDI_SETTARGETGAMMA
title: DXGKDDI_SETTARGETGAMMA
author: windows-driver-content
description: Allows the gamma LUT to be set on a path which is identified by the target id.Note  This is functionally equivalent to the DxgkDdi_UpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_GAMMA_RAMP field is changed. .
old-location: display\dxgkddi_settargetgamma.htm
old-project: display
ms.assetid: 658EA0AA-80FC-4A45-B2EF-DFE928917E7B
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKDDI_SETTARGETGAMMA
req.alt-loc: d3dkmddi.h
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
req.iface: 
---

# DXGKDDI_SETTARGETGAMMA callback



## -description
<p>Allows the gamma LUT to be set on a path which is identified by the target id.<div class="alert"><b>Note</b>  This is functionally equivalent to the DxgkDdi_UpdateActiveVidPnPresentPath in previous WDDM versions if only the D3DKMDT_GAMMA_RAMP field is changed.</div>
<div> </div>
</p>


## -prototype

````
NTSTATUS NTSTATUS DXGKDDI_SETTARGETGAMMA(
  _In_ const HANDLE                  hAdapter,
  _In_ const PDXGKARG_SETTARGETGAMMA pSetTargetGammaArg
);
````


## -parameters
<dl>

### -param <i>hAdapter</i> [in]

<dd>
<p>A handle that identifies the adapter.</p>
</dd>

### -param <i>pSetTargetGammaArg</i> [in]

<dd>
<p>A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi--dxgkarg-settargetgamma.md">DXGKARG_SETTARGETGAMMA</a> structure that provides the target id to be modified and provides the gamma ramp to be set.</p>
</dd>
</dl>

## -returns
<p>If this routine succeeds, it returns STATUS_SUCCESS. </p>

## -remarks
<p>This function is always called at PASSIVE level so the supporting code should be made pageable.</p>

<p>This function is always called at PASSIVE level so the supporting code should be made pageable.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>