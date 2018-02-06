---
UID: NS:wwan._WWAN_IPV6_ADDRESS
title: "_WWAN_IPV6_ADDRESS"
author: windows-driver-content
description: The WWAN_IPV6_ADDRESS structure represents an IPV6 address of a PDP context.
old-location: netvista\wwan_ipv6_address.htm
old-project: netvista
ms.assetid: 3DAC7E30-B938-429C-B389-59F924216B04
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PWWAN_IPV6_ADDRESS, _WWAN_IPV6_ADDRESS, wwan/WWAN_IPV6_ADDRESS, PWWAN_IPV6_ADDRESS, WWAN_IPV6_ADDRESS, netvista.wwan_ipv6_address, WWAN_IPV6_ADDRESS structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_IPV6_ADDRESS, PWWAN_IPV6_ADDRESS structure pointer [Network Drivers Starting with Windows Vista]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_IPV6_ADDRESS
product: Windows
targetos: Windows
req.typenames: WWAN_IPV6_ADDRESS, *PWWAN_IPV6_ADDRESS
req.product: Windows 10 or later.
---

# _WWAN_IPV6_ADDRESS structure
The WWAN_IPV6_ADDRESS structure represents an IPV6 address of a PDP context.

## Syntax
````
typedef struct _WWAN_IPV6_ADDRESS {
  ULONG OnLinkPrefixLength;
  UCHAR IPV6Address[16];
} WWAN_IPV6_ADDRESS, *PWWAN_IPV6_ADDRESS;
````

## Members


`IPV6Address`



`OnLinkPrefixLength`

The length of the prefix or network part of the IP address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 8.1 and later versions of Windows. Available in Windows 8.1 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |