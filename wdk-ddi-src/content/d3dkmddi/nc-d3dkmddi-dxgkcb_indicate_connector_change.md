---
UID: NC.d3dkmddi.DXGKCB_INDICATE_CONNECTOR_CHANGE
title: DXGKCB_INDICATE_CONNECTOR_CHANGE
author: windows-driver-content
description: DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query.
old-location: display\dxgkcb_indicate_connector_change.htm
old-project: display
ms.assetid: D3C76DC0-7A6B-4E1E-8277-F6410D4B474B
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
req.alt-api: *DXGKCB_INDICATE_CONNECTOR_CHANGE
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
req.irql: DISPATCH_LEVEL
---

# DXGKCB_INDICATE_CONNECTOR_CHANGE callback



## -description
DXGKCB_INDICATE_CONNECTOR_CHANGE is called by the KMD to indicate that it has added changes to its change queue which the OS should now query.



## -prototype

````
NTSTATUS APIENTRY *DXGKCB_INDICATE_CONNECTOR_CHANGE(
  _In_ const HANDLE hAdapter
);
````


## -parameters

### -param hAdapter [in]

A handle that identifies the adapter.


## -returns
If this routine succeeds, it returns STATUS_SUCCESS. 


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
DISPATCH_LEVEL

</td>
</tr>
</table>