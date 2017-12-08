---
UID: NS.d3dumddi._D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
title: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
author: windows-driver-content
description: The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses.
old-location: display\d3dddiarg_authenticatedchannelkeyexchange.htm
old-project: display
ms.assetid: 99a86339-62ce-48fd-a1f4-5c3061e624b5
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE, D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE
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
req.iface: 
---

# D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure



## -description
<p>The D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure describes a buffer that contains the session key, which the authenticated channel uses. </p>


## -syntax

````
typedef struct _D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE {
  HANDLE hChannel;
  UINT   DataSize;
  VOID   *pData;
} D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE;
````


## -struct-fields
<dl>

### -field hChannel

<dd>
<p>[in] A handle to the authenticated channel that the runtime creates when the runtime calls the driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createauthenticatedchannel.md">CreateAuthenticatedChannel</a> function. </p>
</dd>

### -field DataSize

<dd>
<p>[in/out] The size, in bytes, of the data that the <b>pData</b> member points to. </p>
</dd>

### -field pData

<dd>
<p>[in/out] A pointer to a buffer that contains the session key. </p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE is supported beginning with the Windows 7 operating system.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-authenticatedchannelkeyexchange.md">AuthenticatedChannelKeyExchange</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi-createauthenticatedchannel.md">CreateAuthenticatedChannel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_AUTHENTICATEDCHANNELKEYEXCHANGE structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
