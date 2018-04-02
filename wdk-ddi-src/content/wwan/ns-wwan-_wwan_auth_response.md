---
UID: NS:wwan._WWAN_AUTH_RESPONSE
title: "_WWAN_AUTH_RESPONSE"
author: windows-driver-content
description: The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.
old-location: netvista\wwan_auth_response.htm
old-project: netvista
ms.assetid: CD0B90A1-032D-4F09-827F-E80607AE4EA7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE, PWWAN_AUTH_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_RESPONSE, WWAN_AUTH_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_RESPONSE, netvista.wwan_auth_response, wwan/PWWAN_AUTH_RESPONSE, wwan/WWAN_AUTH_RESPONSE"
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
-	WWAN_AUTH_RESPONSE
product:
- Windows
targetos: Windows
req.typenames: WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_RESPONSE structure
The WWAN_AUTH_RESPONSE structure represents an authentication challenge response.

## Syntax
```
typedef struct _WWAN_AUTH_RESPONSE {
  WWAN_AUTH_METHOD AuthMethod;
  union {
    WWAN_AUTH_AKA_RESPONSE  AuthAka;
    WWAN_AUTH_AKAP_RESPONSE AuthAkap;
    WWAN_AUTH_SIM_RESPONSE  AuthSim;
  } u;
} WWAN_AUTH_RESPONSE, *PWWAN_AUTH_RESPONSE;
```

## Members


`AuthMethod`

The authentication challenge method used.

`u`

The container union for the different authentication challenge methods.



#### AuthSim

The esponse from the SIM authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthSim</i>, use this member.



#### AuthAka

The response from the AKA authentication method. If <b>AuthMethod</b> is set to <i>WwanAuthAka, </i>use this member.



#### AuthAkap

The response from the AKA' authentication method.  If <b>AuthMethod</b> is set to <i>WwanAuthAkap, </i>use this member.

## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439834">NDIS_WWAN_AUTH_RESPONSE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439834">NDIS_WWAN_AUTH_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh440303">WWAN_AUTH_AKAP_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464126">WWAN_AUTH_AKA_RESPONSE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464128">WWAN_AUTH_METHOD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh464131">WWAN_AUTH_SIM_RESPONSE</a>