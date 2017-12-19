---
UID: NE.wwan._WWAN_IP_TYPE
title: _WWAN_IP_TYPE
author: windows-driver-content
description: The WWAN_IP_TYPE enumeration lists the different levels of supported IP.
old-location: netvista\wwan_ip_type.htm
old-project: NetVista
ms.assetid: E4CE7BE7-021A-4C9A-B467-B63AACEC1266
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WWAN_IP_TYPE, WWAN_IP_TYPE, PWWAN_IP_TYPE, *PWWAN_IP_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WWAN_IP_TYPE
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

# _WWAN_IP_TYPE enumeration



## -description
The WWAN_IP_TYPE enumeration lists the different levels of supported IP.



## -syntax

````
typedef enum _WWAN_IP_TYPE { 
  WwanIPTypeDefault  = 0,
  WwanIPTypeIPv4     = ,
  WwanIPTypeIPv6     = ,
  WwanIPTypeIpv4v6   = 
} WWAN_IP_TYPE;
````


## -enum-fields

### -field WwanIPTypeDefault

Default IP.


### -field WwanIPTypeIPv4

IPv4.


### -field WwanIPTypeIPv6

IPv6


### -field WwanIPTypeIpv4v6

IPv4 with IPv6


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8 and later versions of Windows.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_set_context_state">WWAN_SET_CONTEXT_STATE</a>
</dt>
<dt>
<a href="netvista.wwan_context_state">WWAN_CONTEXT_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WWAN_IP_TYPE enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

