---
UID: NC.d3dumddi.PFND3DDDI_CREATECRYPTOSESSION
title: PFND3DDDI_CREATECRYPTOSESSION
author: windows-driver-content
description: The CreateCryptoSession function creates a crypto session that the Direct3D runtime uses to manage a session key and to perform crypto operations into and out of protected memory.
old-location: display\createcryptosession.htm
old-project: display
ms.assetid: 85d4ae6c-059d-4256-bdda-18de3d20537a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CreateCryptoSession
req.alt-loc: d3dumddi.h
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
---

# PFND3DDDI_CREATECRYPTOSESSION callback



## -description
The <b>CreateCryptoSession</b> function creates a crypto session that the Direct3D runtime uses to manage a session key and to perform crypto operations into and out of protected memory. 


## -prototype

````
PFND3DDDI_CREATECRYPTOSESSION CreateCryptoSession;

__checkReturn HRESULT APIENTRY CreateCryptoSession(
  _In_    HANDLE                        hDevice,
  _Inout_ D3DDDIARG_CREATECRYPTOSESSION *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).

### -param pData [in, out]

 A pointer to a <a href="display.d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information in the structure that the Microsoft Direct3D runtime can use. 

## -returns
<b>CreateCryptoSession</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The crypto session is successfully created. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createcryptosession.md">CreateCryptoSession</a> could not allocate the required memory for it to complete.
<dl>
<dt><b>D3DDDIERR_NOTAVAILABLE</b></dt>
</dl>The driver does not support the GUID that is specified in the <b>CryptoType</b> member of the <a href="display.d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure or the NULL_GUID (all zeros) is specified in the <b>CryptoType</b> member. 
<dl>
<dt><b>D3DDDIERR_UNSUPPORTEDCRYPTO</b></dt>
</dl>The driver does not support the crypto type for the specified decode type. 

 

## -remarks
If the <b>DecodeProfile</b> member of the <a href="display.d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> structure is NULL_GUID, the crypto session will not be used for DirectX Video Acceleration (DirectX VA) decoding. If <b>DecodeProfile</b> is not <b>NULL</b> GUID, the driver should fail with D3DDDIERR_UNSUPPORTEDCRYPTO if the crypto type in the <b>CryptoType</b> member is not supported by the decode profile. 

The driver returns a handle for the crypto session in the <b>hCryptoSession</b> member of <a href="display.d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a> that the runtime passes in all subsequent crypto session calls (for example, <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange.md">CryptoSessionKeyExchange</a>). 

The driver must keep track of the display device (<b>hDevice</b>) that was used to create the crypto session. The driver should fail all subsequent calls that use this created crypto session if the display device that is specified in those calls is different from the display device that was used to create the crypto session.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Supported starting with Windows 7.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_cryptosessionkeyexchange.md">CryptoSessionKeyExchange</a>
</dt>
<dt>
<a href="display.d3dddiarg_createcryptosession">D3DDDIARG_CREATECRYPTOSESSION</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_CREATECRYPTOSESSION callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
