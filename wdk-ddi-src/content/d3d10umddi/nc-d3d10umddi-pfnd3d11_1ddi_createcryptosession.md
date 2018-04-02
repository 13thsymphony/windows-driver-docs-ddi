---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATECRYPTOSESSION
title: PFND3D11_1DDI_CREATECRYPTOSESSION
author: windows-driver-content
description: Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.
old-location: display\createcryptosession1.htm
old-project: display
ms.assetid: 3c31efc3-b844-4e51-947d-b48f36020766
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateCryptoSession, CreateCryptoSession callback function [Display Devices], PFND3D11_1DDI_CREATECRYPTOSESSION, d3d10umddi/CreateCryptoSession, display.createcryptosession1
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
-	CreateCryptoSession
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CREATECRYPTOSESSION callback function
Creates a cryptographic session to encrypt video content that is sent to the display miniport driver.

## Syntax

```
PFND3D11_1DDI_CREATECRYPTOSESSION Pfnd3d111DdiCreatecryptosession;

HRESULT Pfnd3d111DdiCreatecryptosession(
  D3D10DDI_HDEVICE hDevice,
  CONST D3D11_1DDIARG_CREATECRYPTOSESSION *pCreateData,
  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  D3D11_1DDI_HRTCRYPTOSESSION hRTCryptoSession
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*pCreateData`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure. This structure specifies the attributes of the cryptographic session to be created.

`hCryptoSession`

A handle to the driver's private data for the cryptographic session. For more information, see the Remarks section.

`hRTCryptoSession`

A handle to the cryptographic session that the driver should use when it calls back into the Direct3D runtime.


## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The authenticated channel was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDCRYPTO</b></dt>
</dl>
</td>
<td width="60%">
A cryptographic type was specified that is not supported by the decode profile.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.

</td>
</tr>
</table>

## Remarks

The Direct3D runtime calls <i>CreateCryptoSession</i> to create a cryptographic session that the runtime uses to manage a session key and to perform cryptographic operations for video content that is stored in protected memory. 


The  runtime calls <i>CreateCryptoSession</i> after it has called the driver's <a href="https://msdn.microsoft.com/9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca">CalcPrivateCryptoSessionSize</a> to determine the size in bytes for the private data that the driver requires for the cryptographic session. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the cryptographic session.

When the runtime  calls <i>CreateCryptoSession</i>, it passes the handle to the private data memory in the <i>hCryptoSession</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>, if the display device that is specified in those calls is different from the display device that was used to create the cryptographic session. 



If the <b>DecodeProfile</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a> structure is set to <b>NULL_GUID</b>, the cryptographic session will not be used for DirectX Video Acceleration (DXVA) decoding. If <b>DecodeProfile</b> is not set to <b>NULL_GUID</b>, the driver should fail the call with <b>D3DDDIERR_UNSUPPORTEDCRYPTO</b> if the <b>CryptoType</b> member is set to a cryptographic type that is not supported by the decode profile.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/9ca0fdd5-a724-4d5d-81b2-8885b2aed1ca">CalcPrivateCryptoSessionSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406308">D3D11_1DDIARG_CREATECRYPTOSESSION</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>