---
UID: NC.d3dumddi.PFND3DDDI_UNLOCK2CB
title: PFND3DDDI_UNLOCK2CB
author: windows-driver-content
description: The pfnUnlock2Cb function unlocks an allocation that was locked by a call to the pfnLock2Cb function.
old-location: display\pfnunlock2cb.htm
old-project: display
ms.assetid: 642C6A05-DA8C-453A-B1AA-030C59F32DA5
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnUnlock2Cb
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_UNLOCK2CB callback



## -description
The <b>pfnUnlock2Cb</b> function unlocks an allocation that was locked by a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lock2cb.md">pfnLock2Cb</a> function.


## -prototype

````
PFND3DDDI_UNLOCK2CB pfnUnlock2Cb;

HRESULT APIENTRY CALLBACK* pfnUnlock2Cb(
  _In_       HANDLE           hDevice,
  _In_ const D3DDDICB_UNLOCK2 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).

### -param pData [in]

A pointer to a <a href="display.d3dddicb_unlock2">D3DDDICB_UNLOCK2</a> structure that describes the allocation to unlock.

## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>