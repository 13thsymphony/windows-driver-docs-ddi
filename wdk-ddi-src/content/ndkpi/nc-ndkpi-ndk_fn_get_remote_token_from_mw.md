---
UID: NC.ndkpi.NDK_FN_GET_REMOTE_TOKEN_FROM_MW
title: NDK_FN_GET_REMOTE_TOKEN_FROM_MW
author: windows-driver-content
description: The NdkGetRemoteTokenFromMw (NDK_FN_GET_REMOTE_TOKEN_FROM_MW) function gets a memory token from a remote NDK memory window (MW).
old-location: netvista\ndk_fn_get_remote_token_from_mw.htm
old-project: NetVista
ms.assetid: 893B53DA-B858-4E21-9DD9-D244702ACF46
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdkGetRemoteTokenFromMw
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback



## -description
The <i>NdkGetRemoteTokenFromMw</i> (<i>NDK_FN_GET_REMOTE_TOKEN_FROM_MW</i>) function gets a memory token from a remote NDK memory window (MW).



## -prototype

````
NDK_FN_GET_REMOTE_TOKEN_FROM_MW NdkGetRemoteTokenFromMw;

UINT32 NdkGetRemoteTokenFromMw(
  _In_ NDK_MW *pNdkMw
)
{ ... }
````


## -parameters

### -param pNdkMw [in]

A pointer to an NDK memory window (MW) object (<a href="netvista.ndk_mw">NDK_MW</a>).


## -returns
The 
     <i>NdkGetRemoteTokenFromMw</i> function returns a remote memory region token.


## -remarks
 After an <i>NdkBind</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a>) call returns control to the caller, <i>NdkGetRemoteTokenFromMw</i> can be called to retrieve the remote token.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

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
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_bind.md">NDK_FN_BIND</a>
</dt>
<dt>
<a href="netvista.ndk_mw">NDK_MW</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_GET_REMOTE_TOKEN_FROM_MW callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

