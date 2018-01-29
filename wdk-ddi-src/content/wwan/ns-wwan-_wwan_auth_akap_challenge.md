---
UID : NS:wwan._WWAN_AUTH_AKAP_CHALLENGE
title : _WWAN_AUTH_AKAP_CHALLENGE
author : windows-driver-content
description : The WWAN_AUTH_AKAP_CHALLENGE structure represents an authentication challenge using the AKA' method.
old-location : netvista\wwan_auth_akap_challenge.htm
old-project : netvista
ms.assetid : 0C1862D6-1252-4CF7-926A-C4647D545255
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : _WWAN_AUTH_AKAP_CHALLENGE, *PWWAN_AUTH_AKAP_CHALLENGE, PWWAN_AUTH_AKAP_CHALLENGE, WWAN_AUTH_AKAP_CHALLENGE, netvista.wwan_auth_akap_challenge, WWAN_AUTH_AKAP_CHALLENGE structure [Network Drivers Starting with Windows Vista], wwan/PWWAN_AUTH_AKAP_CHALLENGE, PWWAN_AUTH_AKAP_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], wwan/WWAN_AUTH_AKAP_CHALLENGE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wwan.h
req.include-header : Wwan.h
req.target-type : Windows
req.target-min-winverclnt : Supported starting with  Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WWAN_AUTH_AKAP_CHALLENGE, *PWWAN_AUTH_AKAP_CHALLENGE
req.product : Windows 10 or later.
---

# _WWAN_AUTH_AKAP_CHALLENGE structure
The WWAN_AUTH_AKAP_CHALLENGE structure represents an authentication challenge using the AKA' method.

## Syntax
````
typedef struct _WWAN_AUTH_AKAP_CHALLENGE {
  BYTE  Rand[WWAN_AUTH_RAND_LEN];
  BYTE  Autn[WWAN_AUTH_AUTN_LEN];
  BYTE  NetworkName[WWAN_AUTH_NETWORK_NAME_MAX_LEN];
  ULONG NetworkNameLength;
} WWAN_AUTH_AKAP_CHALLENGE, *PWWAN_AUTH_AKAP_CHALLENGE;
````

## Members


`Autn`



`NetworkName`



`NetworkNameLength`

The length, in bytes, of the access network  returned in <b>NetworkName</b>.

`Rand`



## Remarks
The <a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_auth_challenge.md">WWAN_AUTH_CHALLENGE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_AKAP_CHALLENGE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>