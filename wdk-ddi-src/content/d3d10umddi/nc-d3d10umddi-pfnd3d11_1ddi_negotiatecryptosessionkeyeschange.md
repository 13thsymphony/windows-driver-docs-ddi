---
UID: NC.d3d10umddi.PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE
title: PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE
author: windows-driver-content
description: Establishes a session key for a cryptographic session object.
old-location: display\negotiatecryptosessionkeyexchange.htm
old-project: display
ms.assetid: a48dcbae-3236-4523-bc14-4be694da9a7b
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: NegotiateCryptoSessionKeyExchange
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE callback



## -description
Establishes a session key for a cryptographic session object.



## -prototype

````
PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE NegotiateCryptoSessionKeyExchange;

HRESULT APIENTRY* NegotiateCryptoSessionKeyExchange(
  _In_ D3D10DDI_HDEVICE          hDevice,
  _In_ D3D11_1DDI_HCRYPTOSESSION hCryptoSession,
  _In_ UINT                      DataSize,
  _In_ VOID                      *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hCryptoSession [in]

A handle to the cryptographic session object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a> function. 




### -param DataSize [in]

The size, in bytes, of the data in the <i>pData</i> array.




### -param pData [in]

A pointer to a byte array that contains the encrypted session key.


## -returns
<i>NegotiateCryptoSessionKeyExchange</i> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The session key for the cryptographic session was negotiated successfully.
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>Parameters were validated and determined to be incorrect.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

 


## -remarks
The <i>pData</i> parameter references a buffer that contains a session key for the cryptographic session. The key exchange mechanism depends on the type of the encryption algorithm that is used by the cryptographic session.

For sessions that use the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm, the key buffer must contain 256 bytes of data and must be encrypted by using the RSA Encryption Scheme - Optimal Asymmetric Encryption Padding (RSAES-OAEP) algorithm with the public key from the cryptographic session certificate.

The key exchange for a cryptographic session is identical to the key exchange for the Output Protection Manager (OPM) interface. However,  the OPM key buffer contains additional data besides the session key.  


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
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
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createcryptosession.md">CreateCryptoSession</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_NEGOTIATECRYPTOSESSIONKEYESCHANGE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

