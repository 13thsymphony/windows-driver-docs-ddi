---
UID: NS.WWAN._WWAN_GET_VISIBLE_PROVIDERS
title: _WWAN_GET_VISIBLE_PROVIDERS
author: windows-driver-content
description: The WWAN_GET_VISIBLE_PROVIDERS structure provides information about the type of visible providers to return.
old-location: netvista\wwan_get_visible_providers.htm
old-project: netvista
ms.assetid: 62516178-11F9-43F3-A70D-42C8FDDAE2DB
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WWAN_GET_VISIBLE_PROVIDERS, WWAN_GET_VISIBLE_PROVIDERS, *PWWAN_GET_VISIBLE_PROVIDERS
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
req.alt-api: WWAN_GET_VISIBLE_PROVIDERS
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

# _WWAN_GET_VISIBLE_PROVIDERS structure



## -description
The WWAN_GET_VISIBLE_PROVIDERS structure provides information about the type of visible providers to return.


## -syntax

````
typedef struct _WWAN_GET_VISIBLE_PROVIDERS {
  ULONG Action;
} WWAN_GET_VISIBLE_PROVIDERS, *PWWAN_GET_VISIBLE_PROVIDERS;
````


## -struct-fields

### -field Action

Provides information about the type of visible providers to return. The following values are defined:
<table></table>
 
<table>
<tr>
<td>
<b>Value</b>
</td>
<td>
<b>Meaning</b>
</td>
</tr>
<tr>
<td>
WWAN_GET_VISIBLE_PROVIDERS_ALL
</td>
<td>
All providers that are currently visible should be returned.
</td>
</tr>
<tr>
<td>
WWAN_GET_VISIBLE_PROVIDERS_MULTICARRIER
</td>
<td>
Only providers that are currently visible and that can be set as home provider should be returned.
</td>
</tr>
</table>
 

## -remarks


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
<a href="netvista.ndis_wwan_get_visible_providers">NDIS_WWAN_GET_VISIBLE_PROVIDERS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_GET_VISIBLE_PROVIDERS structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
