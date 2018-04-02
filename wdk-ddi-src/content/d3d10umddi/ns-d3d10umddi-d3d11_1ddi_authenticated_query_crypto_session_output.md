---
UID: NS:d3d10umddi.D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
title: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
author: windows-driver-content
description: Contains the response to a QueryAuthenticatedChannel(D3D11_1) query with a D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT.QueryType value of D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION.
old-location: display\d3d11_1ddi_authenticated_query_crypto_session_output.htm
old-project: display
ms.assetid: 3ea5c3e9-44cd-4cf6-be01-4a8c0ce481b0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT, D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT structure [Display Devices], d3d10umddi/D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT, display.d3d11_1ddi_authenticated_query_crypto_session_output
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT
---

# D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT structure
Contains the response to a <a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a> query with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>.<b>QueryType</b> value of <b>D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION</b>.

## Syntax
```
typedef struct D3D11_1DDI_AUTHENTICATED_QUERY_CRYPTO_SESSION_OUTPUT {
  D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT Output;
  HANDLE                                DecodeHandle;
  HANDLE                                CryptoSessionHandle;
  HANDLE                                DeviceHandle;
};
```

## Members


`Output`

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a> structure that contains a Message Authentication Code (MAC) and other data.

`DecodeHandle`

A handle to a decode device.

`CryptoSessionHandle`

A handle to the cryptographic session that is associated with the decode device.

`DeviceHandle`

A handle to the Direct3D device that is associated with the decode device.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406401">D3D11_1DDI_AUTHENTICATED_QUERY_OUTPUT</a>



<a href="https://msdn.microsoft.com/bb152e3d-497f-4798-86cc-6f300e24a05c">QueryAuthenticatedChannel(D3D11_1)</a>