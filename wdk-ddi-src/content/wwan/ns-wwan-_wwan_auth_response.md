---
UID: NS.WWAN._WWAN_AUTH_RESPONSE
title: _WWAN_AUTH_RESPONSE
author: windows-driver-content
description: The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.
old-location: netvista\wwan_auth_response.htm
old-project: netvista
ms.assetid: CD0B90A1-032D-4F09-827F-E80607AE4EA7
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE, WWAN_AUTH_RESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_AUTH_RESPONSE
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_AUTH_RESPONSE structure



## -description
The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.



## -syntax

````
typedef struct _WWAN_AUTH_RESPONSE {
  WWAN_AUTH_METHOD AuthMethod;
  union {
    WWAN_AUTH_SIM_RESPONSE  AuthSim;
    WWAN_AUTH_AKA_RESPONSE  AuthAka;
    WWAN_AUTH_AKAP_RESPONSE AuthAkap;
  } u;
} WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE;
````


## -struct-fields

### -field AuthMethod

The authentication challenge method used.


### -field u

The container union for the different authentication challenge methods.


### -field AuthSim

The esponse from the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.


### -field AuthAka

The response from the AKA authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAka, </i>use this member.


### -field AuthAkap

The response from the AKA' authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAkap, </i>use this member.

</dd>
</dl>

## -remarks
The <a href="netvista.ndis_wwan_auth_response">NDIS_WWAN_AUTH_RESPONSE</a> structure uses this structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_auth_method">WWAN_AUTH_METHOD</a>
</dt>
<dt>
<a href="netvista.wwan_auth_sim_response">WWAN_AUTH_SIM_RESPONSE</a>
</dt>
<dt>
<a href="netvista.wwan_auth_aka_response">WWAN_AUTH_AKA_RESPONSE</a>
</dt>
<dt>
<a href="netvista.wwan_auth_akap_response">WWAN_AUTH_AKAP_RESPONSE</a>
</dt>
<dt>
<a href="netvista.ndis_wwan_auth_response">NDIS_WWAN_AUTH_RESPONSE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_RESPONSE structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

