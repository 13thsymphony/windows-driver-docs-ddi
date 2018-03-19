---
UID: NC:d3d10umddi.PFND3D10DDI_QUERYGETDATA
title: PFND3D10DDI_QUERYGETDATA
author: windows-driver-content
description: The QueryGetData function polls for the state of a query operation.
old-location: display\querygetdata.htm
old-project: display
ms.assetid: 78ee9813-e23e-4d46-acc4-f2fa88559b03
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_QUERYGETDATA, QueryGetData, QueryGetData callback function [Display Devices], UserModeDisplayDriverDx10_Functions_c1a88bca-7df5-4640-9134-fc893e5c8a0d.xml, d3d10umddi/QueryGetData, display.querygetdata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	QueryGetData
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_QUERYGETDATA callback function
The <i>QueryGetData</i> function polls for the state of a query operation.

## Syntax

```
PFND3D10DDI_QUERYGETDATA Pfnd3d10ddiQuerygetdata;

void Pfnd3d10ddiQuerygetdata(
   D3D10DDI_HDEVICE,
   D3D10DDI_HQUERY,
  VOID *,
  UINT DataSize,
   UINT
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HQUERY`



`*`



`DataSize`

The size, in bytes, of the query data that the <i>pData</i> parameter points to. The user-mode display driver can set <i>DataSize</i> to zero and set <i>pData</i> to <b>NULL</b>. If <i>DataSize</i> is zero, <i>QueryGetData</i> can indicate the state of the query operation (for example, through return codes).

`UINT`




## Return Value

None

The driver can use the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the Remarks section.

## Remarks

After the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a> function to transition a query operation to the "issued" state, the runtime can call <i>QueryGetData</i> to determine if the query operation is still in the "issued" state (DXGI_DDI_ERR_WASSTILLDRAWING) or has transitioned to the "signaled" state (S_OK). If the query operation is in the "signaled" state, <i>QueryGetData</i> can return the query data in the <i>pData</i> parameter; otherwise, <i>pData</i> is unchanged. The driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to indicate the state of the query operation. 

The runtime cannot call <i>QueryGetData</i> with a predicate that was created with D3D10_QUERY_MISCFLAG_PREDICATEHINT through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a> function. 

If a query operation handles work that still resides in partial command buffers, by default, the driver should terminate and submit the partial command buffers. However, the driver should not terminate and submit the buffers if the runtime specified the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the <i>Flags</i> parameter. If the runtime passed the D3D10_DDI_GET_DATA_DO_NOT_FLUSH flag in the <i>Flags</i> parameter and if the query operation handles work that still resides in partial command buffers, the driver can call <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to set only the DXGI_DDI_ERR_WASSTILLDRAWING error code.

When the runtime calls <i>QueryGetData</i> to check for query completion, the driver can pass DXGI_DDI_ERR_WASSTILLDRAWING in a call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a> to indicate that the query is not finished yet. The driver can also pass D3DDDIERR_DEVICEREMOVED in a call to <i>pfnSetErrorCb</i>. The Direct3D runtime will determine that any other errors are critical.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_checkcounter.md">CheckCounter</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_queryend.md">QueryEnd</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_setpredication.md">SetPredication</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md">pfnSetErrorCb</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>