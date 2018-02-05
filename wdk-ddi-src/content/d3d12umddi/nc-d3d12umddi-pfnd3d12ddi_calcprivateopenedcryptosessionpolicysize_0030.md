---
UID : NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030
title : PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030
author : windows-driver-content
description : Used to calculate the size of an opened session policy.
old-location : display\pfnd3d12ddi_calcprivateopenedcryptosessionpolicysize_0030_.htm
old-project : display
ms.assetid : 8D88C470-5C1F-4A72-BFB6-B09C038A07F9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnd3d12ddi_calcprivateopenedcryptosessionpolicysize_0030_, PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030 entry point [Display Devices], PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030, d3d12umddi/PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d12umddi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030 callback function
Used to calculate the size of an opened session policy.

## Syntax

```
PFND3D12DDI_CALCPRIVATEOPENEDCRYPTOSESSIONPOLICYSIZE_0030 Pfnd3d12ddiCalcprivateopenedcryptosessionpolicysize0030;

SIZE_T Pfnd3d12ddiCalcprivateopenedcryptosessionpolicysize0030(
  D3D12DDI_HDEVICE hDrvDevice,
  CONST D3D12DDIARG_OPEN_CRYPTO_SESSION_POLICY_0030 *pArgs
)
{...}
```

## Parameters

`hDrvDevice`

The hardware device being processed.

`*pArgs`

The arguments used to open a session policy.


## Return Value

Returns the size of the session in bytes.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |