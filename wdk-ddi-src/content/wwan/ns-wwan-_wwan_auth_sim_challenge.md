---
UID: NS:wwan._WWAN_AUTH_SIM_CHALLENGE
title: "_WWAN_AUTH_SIM_CHALLENGE"
author: windows-driver-content
description: The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.
old-location: netvista\wwan_auth_sim_challenge.htm
old-project: netvista
ms.assetid: E07F3ED0-2F20-40D9-AAAE-49C81168B998
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE, PWWAN_AUTH_SIM_CHALLENGE structure pointer [Network Drivers Starting with Windows Vista], WWAN_AUTH_SIM_CHALLENGE, WWAN_AUTH_SIM_CHALLENGE structure [Network Drivers Starting with Windows Vista], _WWAN_AUTH_SIM_CHALLENGE, netvista.wwan_auth_sim_challenge, wwan/PWWAN_AUTH_SIM_CHALLENGE, wwan/WWAN_AUTH_SIM_CHALLENGE"
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
-	WWAN_AUTH_SIM_CHALLENGE
product:
- Windows
targetos: Windows
req.typenames: WWAN_AUTH_SIM_CHALLENGE, *PWWAN_AUTH_SIM_CHALLENGE
req.product: Windows 10 or later.
---

# _WWAN_AUTH_SIM_CHALLENGE structure
The WWAN_AUTH_SIM_CHALLENGE structure represents an authentication challenge using the SIM method.

## Syntax
```
typedef struct _WWAN_AUTH_SIM_CHALLENGE {
  BYTE  Rand1[WWAN_AUTH_RAND_LEN];
  BYTE  Rand2[WWAN_AUTH_RAND_LEN];
  BYTE  Rand3[WWAN_AUTH_RAND_LEN];
  ULONG n;
} *PWWAN_AUTH_SIM_CHALLENGE, WWAN_AUTH_SIM_CHALLENGE;
```

## Members


`Rand1`



`Rand2`



`Rand3`



`n`

The number of random number challenges.

## Remarks
The <b>n</b> member can be either <b>2</b> or <b>3</b>, according to RFC 4186. If it is set to <b>2</b>, use the <b>Rand1</b> and <b>Rand2</b> members. If it is set to <b>3</b>, then the <b>Rand1</b>, <b>Rand2</b>, and <b>Rand3</b> members.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh464127">WWAN_AUTH_CHALLENGE</a> structure uses this structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh464127">WWAN_AUTH_CHALLENGE</a>