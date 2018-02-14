---
UID: NS:wwan._WWAN_AUTH_AKA_CHALLENGE
title: "_WWAN_AUTH_AKA_CHALLENGE"
author: windows-driver-content
description: The WWAN_AUTH_AKA_CHALLENGE structure represents an authentication challenge using the AKA method.
old-location: netvista\wwan_auth_aka_challenge.htm
old-project: netvista
ms.assetid: A0513766-7D58-4F85-8105-93D7A0D9036B
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*PWWAN_AUTH_AKA_CHALLENGE, WWAN_AUTH_AKA_CHALLENGE, wwan/PWWAN_AUTH_AKA_CHALLENGE, _WWAN_AUTH_AKA_CHALLENGE, PWWAN_AUTH_AKA_CHALLENGE, wwan/WWAN_AUTH_AKA_CHALLENGE, netvista.wwan_auth_aka_challenge, WWAN_AUTH_AKA_CHALLENGE structure [Network Drivers Starting with Windows Vista], PWWAN_AUTH_AKA_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista]"
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
-	WWAN_AUTH_AKA_CHALLENGE
product: Windows
targetos: Windows
req.typenames: "*PWWAN_AUTH_AKA_CHALLENGE, WWAN_AUTH_AKA_CHALLENGE"
req.product: Windows 10 or later.
---

# _WWAN_AUTH_AKA_CHALLENGE structure
The WWAN_AUTH_AKA_CHALLENGE structure represents an authentication challenge using the AKA method.

## Syntax
````
typedef struct _WWAN_AUTH_AKA_CHALLENGE {
  BYTE Rand[WWAN_AUTH_RAND_LEN];
  BYTE Autn[WWAN_AUTH_AUTN_LEN];
} WWAN_AUTH_AKA_CHALLENGE, *PWWAN_AUTH_AKA_CHALLENGE;
````

## Members


`Autn`



`Rand`



## Remarks
The <a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows 8 and later versions of Windows. Versions:\_Supported in Windows 8 and later versions of Windows. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_AKA_CHALLENGE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>