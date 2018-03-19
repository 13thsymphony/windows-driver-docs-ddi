---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
title: PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS
author: windows-driver-content
description: CheckCryptoSessionStatus returns the status of a CryptoSession object.
old-location: display\checkcryptosessionstatus.htm
old-project: display
ms.assetid: C7BA5CE0-F89E-4C4B-9976-B9CB6BF8DA81
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CheckCryptoSessionStatus, CheckCryptoSessionStatus callback function [Display Devices], d3d10umddi/CheckCryptoSessionStatus, display.checkcryptosessionstatus
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	D3d10umddi.h
api_name:
-	CheckCryptoSessionStatus
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS callback function
<b>CheckCryptoSessionStatus</b> returns the status of a <b>CryptoSession</b> object.

## Syntax

```
PFND3DWDDM2_0DDI_CHECKCRYPTOSESSIONSTATUS Pfnd3dwddm20DdiCheckcryptosessionstatus;

void Pfnd3dwddm20DdiCheckcryptosessionstatus(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS *pStatus
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hCryptoSession`

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>DDI.

`*pStatus`

Receives a status as a value of the <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status.md">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a> enumeration.


## Return Value

This callback function does not return a value.

## Remarks

The application may call this DDI after receiving a hardware content protection tear-down notification to determine the state of the underlying hardware key and protected content.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_crypto_session_status.md">D3DWDDM2_0DDI_CRYPTO_SESSION_STATUS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>