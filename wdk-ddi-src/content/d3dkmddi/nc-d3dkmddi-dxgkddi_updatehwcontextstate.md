---
UID: NC.d3dkmddi.DXGKDDI_UPDATEHWCONTEXTSTATE
title: DXGKDDI_UPDATEHWCONTEXTSTATE
author: windows-driver-content
description: Used to update the hardware context state.
old-location: display\dxgkddi_updatehwcontextstate.htm
old-project: display
ms.assetid: 1187A302-CD7D-418E-B48F-74D1FF29C991
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DXGKDDI_UPDATEHWCONTEXTSTATE
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
req.irql: requires_(PASSIVE_LEVEL)
---

# DXGKDDI_UPDATEHWCONTEXTSTATE callback



## -description
Used to update the hardware context state.



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_UPDATEHWCONTEXTSTATE(
  _In_ const HANDLE                        hAdapter,
  _In_ const PDXGKARG_UPDATEHWCONTEXTSTATE pUpdateHwContextState
);
````


## -parameters

### -param hAdapter [in]

A handle to the generated adapter.


### -param pUpdateHwContextState [in]

A pointer used by the function to update the hardware context state.


## -returns
Returns STATUS_SUCCESS if completed successfully.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
requires_(PASSIVE_LEVEL)

</td>
</tr>
</table>