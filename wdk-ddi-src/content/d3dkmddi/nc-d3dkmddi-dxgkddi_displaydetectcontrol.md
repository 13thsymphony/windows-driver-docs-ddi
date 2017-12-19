---
UID: NC.d3dkmddi.DXGKDDI_DISPLAYDETECTCONTROL
title: DXGKDDI_DISPLAYDETECTCONTROL
author: windows-driver-content
description: Used to turn hot plug detection on and off and to initiate status polls on either a specific target or all targets.
old-location: display\dxgkddi_displaydetectcontrol.htm
old-project: display
ms.assetid: 6F10EA4D-BCDE-475E-9937-414CB83F6F2F
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
req.alt-api: DXGKDDI_DISPLAYDETECTCONTROL
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

# DXGKDDI_DISPLAYDETECTCONTROL callback



## -description
Used to turn hot plug detection on and off and to initiate status polls on either a specific target or all targets.  



## -prototype

````
NTSTATUS APIENTRY DXGKDDI_DISPLAYDETECTCONTROL(
  _In_ const HANDLE                          hAdapter,
  _In_ const PDXGKARG_DISPLAYDETECTCONTROL   pDisplayDetectControl
);
````


## -parameters

### -param hAdapter [in]

A handle that identifies the adapter.


### -param pDisplayDetectControl [in]

A pointer to a <a href="display.dxgkarg_displaydetectcontrol">DXGKARG_DISPLAYDETECTCONTROL</a> structure that describes the detection action which is requested.


## -returns
If this routine succeeds, it returns STATUS_SUCCESS.


## -remarks
This function is always called at PASSIVE level so the supporting code should be made pageable.

The status returned only reflects the call, not the status of connectors. If the driver detects a change, it will respond by calling DxgkCbIndicateConnectorChange.  If a poll of one or more targets was requested, the driver should return once the request has been submitted to hardware, rather than waiting for the poll to complete.

DXGK_DDCT_POLLONE applies only to the specified target id while DXGK_DDCT_POLLALL applies to all targets.  It would be an OS error to request either of these types of detection control if HPD is not enabled so the driver can simply fail the call with STATUS_INVALID_PARAMETER.


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