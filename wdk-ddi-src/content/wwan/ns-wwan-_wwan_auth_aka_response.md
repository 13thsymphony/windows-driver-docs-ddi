---
UID: NS:wwan._WWAN_AUTH_AKA_RESPONSE
title: "_WWAN_AUTH_AKA_RESPONSE"
author: windows-driver-content
description: The WWAN_AUTH_AKA_RESPONSE structure represents a response to an AKA authentication challenge.
old-location: netvista\wwan_auth_aka_response.htm
old-project: netvista
ms.assetid: 16F20188-AFAC-46BF-9D90-26376DEF1595
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WWAN_AUTH_AKA_RESPONSE, PWWAN_AUTH_AKA_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], *PWWAN_AUTH_AKA_RESPONSE, _WWAN_AUTH_AKA_RESPONSE, PWWAN_AUTH_AKA_RESPONSE, WWAN_AUTH_AKA_RESPONSE structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_AUTH_AKA_RESPONSE, netvista.wwan_auth_aka_response, wwan/WWAN_AUTH_AKA_RESPONSE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows.
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
-	WWAN_AUTH_AKA_RESPONSE
product: Windows
targetos: Windows
req.typenames: WWAN_AUTH_AKA_RESPONSE, *PWWAN_AUTH_AKA_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_AKA_RESPONSE structure
The WWAN_AUTH_AKA_RESPONSE structure represents a response to an AKA authentication challenge.

## Syntax
````
typedef struct _WWAN_AUTH_AKA_RESPONSE {
  BYTE  Res[WWAN_AUTH_RES_MAX_LEN];
  ULONG ResLength;
  BYTE  IK[WWAN_AUTH_IK_LEN];
  BYTE  CK[WWAN_AUTH_CK_LEN];
  BYTE  Auts[WWAN_AUTH_AUTS_LEN];
} WWAN_AUTH_AKA_RESPONSE, *PWWAN_AUTH_AKA_RESPONSE;
````

## Members


`Auts`



`CK`



`IK`



`Res`



`ResLength`

Length of response in the <b>Res</b> member.

## Remarks
The <a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 and later versions of Windows. Versions:\_Supported in Windows 8 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_AKA_RESPONSE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>