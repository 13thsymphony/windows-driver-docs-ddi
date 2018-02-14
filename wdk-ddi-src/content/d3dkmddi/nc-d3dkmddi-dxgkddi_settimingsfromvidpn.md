---
UID: NC:d3dkmddi.DXGKDDI_SETTIMINGSFROMVIDPN
title: DXGKDDI_SETTIMINGSFROMVIDPN
author: windows-driver-content
description: DXGKDDI_SETTIMINGSFROMVIDPN is called to set or modify the display timings on an adapter. This DDI replaces DxgkDdiCommitVidPn.
old-location: display\dxgkddi_settimingsfromvidpn.htm
old-project: display
ms.assetid: 7E991251-1738-41AD-83D6-60DD7E183D68
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.dxgkddi_settimingsfromvidpn, DXGKDDI_SETTIMINGSFROMVIDPN callback function [Display Devices], DXGKDDI_SETTIMINGSFROMVIDPN, d3dkmddi/DXGKDDI_SETTIMINGSFROMVIDPN
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKDDI_SETTIMINGSFROMVIDPN
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_SETTIMINGSFROMVIDPN function
DXGKDDI_SETTIMINGSFROMVIDPN is called to set or modify the display timings on an adapter. This DDI replaces DxgkDdiCommitVidPn.

## Syntax

```
DXGKDDI_SETTIMINGSFROMVIDPN DxgkddiSettimingsfromvidpn;

NTSTATUS DxgkddiSettimingsfromvidpn(
  IN_CONST_HANDLE hAdapter,
  IN_OUT_PDXGKARG_SETTIMINGSFROMVIDPN pSetTimings
)
{...}
```

## Parameters

`hAdapter`

Identifies the adapter upon which the display timings should be set.

`pSetTimings`

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_settimingsfromvidpn.md">DXGKARG_SETTIMINGSFROMVIDPN</a> structure that describes the display timings to be set.


## Return Value

If this routine succeeds, it returns STATUS_SUCCESS.

<div class="alert"><b>Note</b>  The driver should always return a success code unless there is an error in the parameters or a failure to process the request.  If the driver is unable to set one or more paths as requested, it should describe the condition using the output fields but still report success.</div>
<div> </div>

## Remarks

The kernel mode driver evaluates the parameters and initiates the changes if no conditions prevent attempting them.  If conditions such as exceeding target bandwidth limitations prevent the changes from being made, the driver should describe the conditions.  If changing the timings would be possible but requires preparation work to be completed first, the driver should indicate that in the output flags.

This function is always called at PASSIVE level.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3dkmddi.h |