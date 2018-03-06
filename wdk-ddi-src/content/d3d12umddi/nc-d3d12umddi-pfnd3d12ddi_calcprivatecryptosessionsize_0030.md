---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
title: PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
author: windows-driver-content
description: Used to calculate a private session size.
old-location: display\pfnd3d12ddi_calcprivatecryptosessionsize_0030_.htm
old-project: display
ms.assetid: 5C6A62D2-C4D1-4024-B777-EA4AAC7AC971
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030, PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030, display.pfnd3d12ddi_calcprivatecryptosessionsize_0030_
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 callback function
Used to calculate a private session size.

## Syntax

```
PFND3D12DDI_CALCPRIVATECRYPTOSESSIONSIZE_0030 Pfnd3d12ddiCalcprivatecryptosessionsize0030;

SIZE_T Pfnd3d12ddiCalcprivatecryptosessionsize0030(
  D3D12DDI_HDEVICE hDrvDevice,
  CONST D3D12DDIARG_CREATE_CRYPTO_SESSION_0030 *pArgs
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`*pArgs`

The arguments used to create a session.


## Return Value

Returns the size of the session in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |