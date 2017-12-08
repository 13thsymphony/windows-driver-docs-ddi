---
UID: NC.d3dkmddi.DXGKDDI_GETMULTIPLANEOVERLAYCAPS
title: DXGKDDI_GETMULTIPLANEOVERLAYCAPS
author: windows-driver-content
description: Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes.
old-location: display\dxgkddi_getmultiplaneoverlaycaps.htm
old-project: display
ms.assetid: 17A9B769-D280-491D-844E-A9B2C66D2207
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: DXGKDDI_GETMULTIPLANEOVERLAYCAPS
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
---

# DXGKDDI_GETMULTIPLANEOVERLAYCAPS callback



## -description
Called to retrieve multiplane overlay capabilities. Support for this DDI is required for any WDDM 2.2 driver that wants to support multiple planes. 


## -prototype

````
NTSTATUS APIENTRY DXGKDDI_GETMULTIPLANEOVERLAYCAPS(
  _In_ const HANDLE                            hAdapter,
  _In_ const PDXGKARG_GETMULTIPLANEOVERLAYCAPS pGetMultiPlaneOverlayCaps
);
````


## -parameters

### -param hAdapter [in]

Identifies the adapter containing the overlay hardware.

### -param pGetMultiPlaneOverlayCaps [in]

A pointer to a DXGKARG_GETMULTIPLANEOVERLAYCAPS structure that receives the driver capabilities.

## -returns
DXGKDDI_GETMULTIPLANEOVERLAYCAPS returns the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>If the routine has been successfully completed.

 

## -remarks
This function is called at PASSIVE_LEVEL.

The multiplane overlay capabilities are allowed to change due to display configuration changes.

For WDDM 2.2 drivers, this DDI is used to retrieve the multiplane overlay capabilities rather than the user mode DDIs. 


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
</table>