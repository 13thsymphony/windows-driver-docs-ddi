---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETENCRYPTIONBLTKEY
title: PFND3D11_1DDI_GETENCRYPTIONBLTKEY
author: windows-driver-content
description: Queries the key that is used to decrypt the data returned by the EncryptionBlt(D3D11_1) function.
old-location: display\getencryptionbltkey1.htm
old-project: display
ms.assetid: f1d3a443-7980-4894-b6a9-04c0886c6996
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D11_1DDI_GETENCRYPTIONBLTKEY, d3d10umddi/pfnGetEncryptionBltKey, display.getencryptionbltkey1, pfnGetEncryptionBltKey, pfnGetEncryptionBltKey callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,Available in Windows Desktop version 10.0.10030.0
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
-	d3d10umddi.h
api_name:
-	pfnGetEncryptionBltKey
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_GETENCRYPTIONBLTKEY callback function
Queries the key that is used to decrypt the data returned by the <a href="https://msdn.microsoft.com/ea6f1b8c-d65a-4d6d-a7ae-998374bf5bfb">EncryptionBlt(D3D11_1)</a> function.

## Syntax

```
PFND3D11_1DDI_GETENCRYPTIONBLTKEY Pfnd3d111DdiGetencryptionbltkey;

void Pfnd3d111DdiGetencryptionbltkey(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  UINT KeySize,
  VOID *pReadbackKey
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`hCryptoSession`

A handle to the cryptographic session that was created in a call to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a> function.

`KeySize`

The size, in bytes, of the encryption key that the <i>pReadBackKey</i> parameter points to.

`*pReadbackKey`

A pointer to a buffer that contains the encryption key.


## Return Value

This callback function does not return a value.

## Remarks

When the <b>GetEncryptionBltKey</b> function is called, the display miniport driver should generate a new encryption key.  If the cryptographic session is using  the <b>D3DCRYPTOTYPE_AES128_CTR</b> cryptographic type, the driver or graphics adapter should encrypt the data that is referenced by the   <i>pReadbackKey</i> parameter by using the session key with the AES-ECB algorithm.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8,Available in Windows Desktop version 10.0.10030.0 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451619">CreateCryptoSession</a>



<a href="https://msdn.microsoft.com/ea6f1b8c-d65a-4d6d-a7ae-998374bf5bfb">EncryptionBlt(D3D11_1)</a>