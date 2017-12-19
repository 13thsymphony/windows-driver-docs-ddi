---
UID: NS.WWAN._WWAN_IPV6_ADDRESS
title: _WWAN_IPV6_ADDRESS
author: windows-driver-content
description: The WWAN_IPV6_ADDRESS structure represents an IPV6 address of a PDP context.
old-location: netvista\wwan_ipv6_address.htm
old-project: NetVista
ms.assetid: 3DAC7E30-B938-429C-B389-59F924216B04
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WWAN_IPV6_ADDRESS, PWWAN_IPV6_ADDRESS, *PWWAN_IPV6_ADDRESS, WWAN_IPV6_ADDRESS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.1 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_IPV6_ADDRESS
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

# _WWAN_IPV6_ADDRESS structure



## -description
The WWAN_IPV6_ADDRESS structure represents an IPV6 address of a PDP context.



## -syntax

````
typedef struct _WWAN_IPV6_ADDRESS {
  ULONG OnLinkPrefixLength;
  UCHAR IPV6Address[16];
} WWAN_IPV6_ADDRESS, *PWWAN_IPV6_ADDRESS;
````


## -struct-fields

### -field OnLinkPrefixLength

The length of the prefix or network part of the IP address.


### -field IPV6Address[16]

The IPV6 address of the PDP context.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 8.1 and later versions of Windows.

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