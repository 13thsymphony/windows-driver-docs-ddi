---
UID: NS:wwan._WWAN_AUTH_CHALLENGE
title: "_WWAN_AUTH_CHALLENGE"
author: windows-driver-content
description: The WWAN_AUTH_CHALLENGE structure represents an authentication challenge for a specific method.
old-location: netvista\wwan_auth_challenge.htm
old-project: netvista
ms.assetid: A31B9E91-B5F9-4EF3-AD9E-A5E26CBD4B35
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_AUTH_CHALLENGE, PWWAN_AUTH_CHALLENGE, PWWAN_AUTH_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_CHALLENGE, WWAN_AUTH_CHALLENGE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_CHALLENGE, netvista.wwan_auth_challenge, wwan/PWWAN_AUTH_CHALLENGE, wwan/WWAN_AUTH_CHALLENGE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_AUTH_CHALLENGE
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_CHALLENGE, *PWWAN_AUTH_CHALLENGE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_CHALLENGE structure
The WWAN_AUTH_CHALLENGE structure represents an authentication challenge for a specific method.

## Syntax
````
typedef struct _WWAN_AUTH_CHALLENGE {
  WWAN_AUTH_METHOD AuthMethod;
  union {
    WWAN_AUTH_SIM_CHALLENGE  AuthSim;
    WWAN_AUTH_AKA_CHALLENGE  AuthAka;
    WWAN_AUTH_AKAP_CHALLENGE AuthAkap;
  } u;
} WWAN_AUTH_CHALLENGE, *PWWAN_AUTH_CHALLENGE;
````

## Members


`AuthMethod`

The authentication challenge method.

`u`

The container union for the different authentication challenge methods.



#### AuthSim

The challenge that uses the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.



#### AuthAka

The challenge that uses the AKA authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAka</i>, use this member.



#### AuthAkap

The challenge that uses the AKA' authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAkap,</i> use this member.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_auth_akap_challenge.md">WWAN_AUTH_AKAP_CHALLENGE</a>



<a href="..\wwan\ns-wwan-_wwan_auth_aka_challenge.md">WWAN_AUTH_AKA_CHALLENGE</a>



<a href="..\wwan\ne-wwan-_wwan_auth_method.md">WWAN_AUTH_METHOD</a>



<a href="..\wwan\ns-wwan-_wwan_auth_sim_challenge.md">WWAN_AUTH_SIM_CHALLENGE</a>