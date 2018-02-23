---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
title: PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
author: windows-driver-content
description: Used to calculate the size of a protected resource session.
old-location: display\pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0030.htm
old-project: display
ms.assetid: 3D677BE9-32D7-4EA4-988F-83A64CFA3FFC
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.pfnd3d12ddi_calcprivateprotectedresourcesessionsize_0030, PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030 entry point [Display Devices], PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030, d3d12umddi/PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030 callback function
Used to calculate the size of a protected resource session.

## Syntax

```
PFND3D12DDI_CALCPRIVATEPROTECTEDRESOURCESESSIONSIZE_0030 Pfnd3d12ddiCalcprivateprotectedresourcesessionsize0030;

SIZE_T Pfnd3d12ddiCalcprivateprotectedresourcesessionsize0030(
  D3D12DDI_HDEVICE hDrvDevice,
  CONST D3D12DDIARG_CREATE_PROTECTED_RESOURCE_SESSION_0030 *pArgs
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`*pArgs`

The arguments used to open a protected resource session.


## Return Value

Returns the size of the session in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |