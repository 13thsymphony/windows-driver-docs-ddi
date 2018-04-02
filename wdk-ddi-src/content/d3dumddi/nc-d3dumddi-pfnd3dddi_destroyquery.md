---
UID: NC:d3dumddi.PFND3DDDI_DESTROYQUERY
title: PFND3DDDI_DESTROYQUERY
author: windows-driver-content
description: The DestroyQuery function releases resources for a query.
old-location: display\destroyquery.htm
old-project: display
ms.assetid: c4cef278-1771-4903-a5cf-85674463aff8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DestroyQuery, DestroyQuery callback function [Display Devices], PFND3DDDI_DESTROYQUERY, UserModeDisplayDriver_Functions_ce2ecc4e-9e2e-485f-bde3-8800e62c5b8d.xml, d3dumddi/DestroyQuery, display.destroyquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	DestroyQuery
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DESTROYQUERY callback function
The <b>DestroyQuery</b> function releases resources for a query.

## Syntax

```
PFND3DDDI_DESTROYQUERY Pfnd3dddiDestroyquery;

HRESULT Pfnd3dddiDestroyquery(
  HANDLE hDevice,
  CONST HANDLE
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`HANDLE`




## Return Value

<b>DestroyQuery</b> returns S_OK or an appropriate error result if the resources are not released.

## Remarks

The <b>DestroyQuery</b> function notifies the driver to destroy the query handle that the <a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a> function previously created. The driver can then release resources that are associated with the query handle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/ac63b77b-2704-4d5b-bf1d-9d85e8a1e336">CreateQuery</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>