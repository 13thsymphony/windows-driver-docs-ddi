---
UID: NC.d3dumddi.PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE
title: PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE
author: windows-driver-content
description: The AuthenticatedChannelKeyExchange function negotiates the session key.
old-location: display\authenticatedchannelkeyexchange.htm
old-project: display
ms.assetid: 627f9689-1059-4f88-9005-9c7600dad686
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: AuthenticatedChannelKeyExchange is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: AuthenticatedChannelKeyExchange
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

# PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE callback



## -description
The <b>AuthenticatedChannelKeyExchange</b> function negotiates the session key. 



## -prototype

````
PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE AuthenticatedChannelKeyExchange;

__checkReturn HRESULT APIENTRY AuthenticatedChannelKeyExchange(
  _In_    HANDLE                                    hDevice,
  _Inout_ D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context).


### -param pData [in, out]

 A pointer to a <a href="display.d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure that describes a buffer that contains the session key, which the  authenticated channel uses. 


## -returns
<b>AuthenticatedChannelKeyExchange</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The session key is successfully negotiated. 
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_authenticatedchannelkeyexchange.md">AuthenticatedChannelKeyExchange</a> could not allocate the required memory for it to complete.

 


## -remarks
The <b>pData</b> member in the <a href="display.d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a> structure points to a buffer that contains a secret key that an application previously RSAES-OAEP-encrypted with the public key from the driver's authenticated channel certificate. The actual size of the buffer is 256 bytes. This exchange is identical to how the <a href="https://msdn.microsoft.com/2c138dbd-55ca-4c71-8c8b-b2efd1ca80f2">Output Protection Manager</a> (OPM) key exchange works, except the OPM buffer contains additional data besides the session key. The same certificate that is used for OPM key exchange can be used for the authenticated channel. 

The driver decrypts this secret key and uses the secret key in calls to the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_configureauthenicatedchannel.md">ConfigureAuthenticatedChannel</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryauthenticatedchannel.md">QueryAuthenticatedChannel</a> functions to calculate One-key Cipher Block Chaining (CBC)-mode message authentication codes (OMACs). 


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
AuthenticatedChannelKeyExchange is supported beginning with the Windows 7 operating system.

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
<a href="display.d3dddiarg_authenticatedchannelkeyexchange">D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_AUTHENTICATEDCHANNELKEYEXCHANGE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

