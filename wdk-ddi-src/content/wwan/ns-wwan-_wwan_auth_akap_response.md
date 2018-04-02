---
UID: NS:wwan._WWAN_AUTH_AKAP_RESPONSE
title: "_WWAN_AUTH_AKAP_RESPONSE"
author: windows-driver-content
description: The WWAN_AUTH_AKAP_RESPONSE structure represents a response to an AKA' (AKA Prime) authentication challenge.
old-location: netvista\wwan_auth_akap_response.htm
old-project: netvista
ms.assetid: 5BD4AC50-6029-41BE-A825-9290189F29B8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_AUTH_AKAP_RESPONSE, PWWAN_AUTH_AKAP_RESPONSE, PWWAN_AUTH_AKAP_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_AKAP_RESPONSE, WWAN_AUTH_AKAP_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_AKAP_RESPONSE, netvista.wwan_auth_akap_response, wwan/PWWAN_AUTH_AKAP_RESPONSE, wwan/WWAN_AUTH_AKAP_RESPONSE"
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
-	WWAN_AUTH_AKAP_RESPONSE
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_AKAP_RESPONSE, *PWWAN_AUTH_AKAP_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_AKAP_RESPONSE structure
The WWAN_AUTH_AKAP_RESPONSE structure represents a response to an AKA' (AKA Prime) authentication challenge.

## Syntax
```
typedef struct _WWAN_AUTH_AKAP_RESPONSE {
  BYTE  Res[WWAN_AUTH_RES_MAX_LEN];
  ULONG ResLength;
  BYTE  IKP[WWAN_AUTH_IK_LEN];
  BYTE  CKP[WWAN_AUTH_CK_LEN];
  BYTE  Auts[WWAN_AUTH_AUTS_LEN];
} WWAN_AUTH_AKAP_RESPONSE, *PWWAN_AUTH_AKAP_RESPONSE;
```

## Members


`Res`



`ResLength`

The length of the response in the <b>Res</b> member.

`IKP`



`CKP`



`Auts`



## Remarks
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464129">WWAN_AUTH_RESPONSE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh464129">WWAN_AUTH_RESPONSE</a>