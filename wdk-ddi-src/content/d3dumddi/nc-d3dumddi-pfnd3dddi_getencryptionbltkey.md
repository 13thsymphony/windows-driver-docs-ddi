---
UID : NC:d3dumddi.PFND3DDDI_GETENCRYPTIONBLTKEY
title : PFND3DDDI_GETENCRYPTIONBLTKEY
author : windows-driver-content
description : The GetEncryptionBltKey function returns the key that is used to decrypt the data that the driver's EncryptionBlt function returns.
old-location : display\getencryptionbltkey.htm
old-project : display
ms.assetid : b3c3e792-bc8a-485e-a208-66b7d921cc15
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXGK_PTE, DXGK_PTE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : GetEncryptionBltKey is supported beginning with the Windows 7 operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GetEncryptionBltKey
req.alt-loc : d3dumddi.h
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_GETENCRYPTIONBLTKEY callback function
The <i>GetEncryptionBltKey</i> function returns the key that is used to decrypt the data that the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a> function returns.

## Syntax

```
PFND3DDDI_GETENCRYPTIONBLTKEY Pfnd3dddiGetencryptionbltkey;

HRESULT Pfnd3dddiGetencryptionbltkey(
  HANDLE hDevice,
  CONST D3DDDIARG_GETENCRYPTIONBLTKEY *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

<i>GetEncryptionBltKey</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The key for an encrypted session is successfully retrieved. 
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the <i>GetEncryptionBltKey</i> function.

## Remarks

The hardware and driver can optionally support the <i>GetEncryptionBltKey</i> function for all crypto types.  

Each time the Direct3D runtime calls the driver's <i>GetEncryptionBltKey</i> function, the driver should generate a new read-back key. If the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> function previously created the encryption session with the <b>CryptoType</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a> structure set to D3DCRYPTOTYPE_AES128_CTR, the driver and hardware should encrypt the read-back key with the session key.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dumddi.h (include D3dumddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createcryptosession.md">D3DDDIARG_CREATECRYPTOSESSION</a>
</dt>
<dt>
<a href="..\d3dumddi\ns-d3dumddi-_getencryptionbltkey.md">D3DDDIARG_GETENCRYPTIONBLTKEY</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_encryptionblt.md">EncryptionBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_GETENCRYPTIONBLTKEY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>