---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
title: PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE
author: windows-driver-content
description: Returns the number of bytes that the driver requires to store private data for the cryptographic session state.
old-location: display\calcprivatecryptosessionsize.htm
old-project: display
ms.assetid: 9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateCryptoSessionSize, CalcPrivateCryptoSessionSize callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE, d3d10umddi/CalcPrivateCryptoSessionSize, display.calcprivatecryptosessionsize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	CalcPrivateCryptoSessionSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE callback function
Returns the number of bytes that the driver requires to store private data for the cryptographic session state.

## Syntax

```
PFND3D11_1DDI_CALCPRIVATECRYPTOSESSIONSIZE Pfnd3d111DdiCalcprivatecryptosessionsize;

SIZE_T Pfnd3d111DdiCalcprivatecryptosessionsize(
  D3D10DDI_HDEVICE hDevice,
  CONST D3D11_1DDIARG_CREATECRYPTOSESSION *pCreateData
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*pCreateData`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure that describes the cryptographic session.


## Return Value

The required number of bytes for the cryptographic session state.

## Remarks

The runtime will validate the members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure before it calls this function.

This function is not expected to fail.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a>