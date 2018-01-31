---
UID : NS:wwan._WWAN_AUTH_AKAP_RESPONSE
title : "_WWAN_AUTH_AKAP_RESPONSE"
author : windows-driver-content
description : The WWAN_AUTH_AKAP_RESPONSE structure represents a response to an AKA' (AKA Prime) authentication challenge.
old-location : netvista\wwan_auth_akap_response.htm
old-project : netvista
ms.assetid : 5BD4AC50-6029-41BE-A825-9290189F29B8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : PWWAN_AUTH_AKAP_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_AKAP_RESPONSE, wwan/PWWAN_AUTH_AKAP_RESPONSE, wwan/WWAN_AUTH_AKAP_RESPONSE, netvista.wwan_auth_akap_response, _WWAN_AUTH_AKAP_RESPONSE, PWWAN_AUTH_AKAP_RESPONSE, WWAN_AUTH_AKAP_RESPONSE structure [Network Drivers Starting with Windows Vista], *PWWAN_AUTH_AKAP_RESPONSE
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
req.typenames : WWAN_AUTH_AKAP_RESPONSE, *PWWAN_AUTH_AKAP_RESPONSE
req.product : Windows 10 or later.
---

# _WWAN_AUTH_AKAP_RESPONSE structure
The WWAN_AUTH_AKAP_RESPONSE structure represents a response to an AKA' (AKA Prime) authentication challenge.

## Syntax
````
typedef struct _WWAN_AUTH_AKAP_RESPONSE {
  BYTE  Res[WWAN_AUTH_RES_MAX_LEN];
  ULONG ResLength;
  BYTE  IKP[WWAN_AUTH_IK_LEN];
  BYTE  CKP[WWAN_AUTH_CK_LEN];
  BYTE  Auts[WWAN_AUTH_AUTS_LEN];
} WWAN_AUTH_AKAP_RESPONSE, *PWWAN_AUTH_AKAP_RESPONSE;
````

## Members


`Auts`



`CKP`



`IKP`



`Res`



`ResLength`

The length of the response in the <b>Res</b> member.

## Remarks
The <a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_auth_response.md">WWAN_AUTH_RESPONSE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_AUTH_AKAP_RESPONSE structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>