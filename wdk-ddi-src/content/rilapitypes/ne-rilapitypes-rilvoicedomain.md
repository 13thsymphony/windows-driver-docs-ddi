---
UID: NE:rilapitypes.RILVOICEDOMAIN
title: RILVOICEDOMAIN
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilvoicedomain_2.htm
old-project: netvista
ms.assetid: bc0e9ba8-c790-402a-900a-7ae2b4f76060
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_VOICE_DOMAIN_MAX, RIL_VOICE_DOMAIN_IMS, RIL_VOICE_DOMAIN_3GPP, rilapitypes/RIL_VOICE_DOMAIN_IMS, RIL_VOICE_DOMAIN_3GPP2, rilapitypes/RIL_VOICE_DOMAIN_3GPP, RILVOICEDOMAIN enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_VOICE_DOMAIN_3GPP2, RILVOICEDOMAIN, RIL_VOICE_DOMAIN_MAX, rilapitypes/RILVOICEDOMAIN, netvista.rilvoicedomain_2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILVOICEDOMAIN
product: Windows
targetos: Windows
req.typenames: RILVOICEDOMAIN
req.product: Windows 10 or later.
---

# RILVOICEDOMAIN Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILVOICEDOMAIN { 
  RIL_VOICE_DOMAIN_3GPP,
  RIL_VOICE_DOMAIN_3GPP2,
  RIL_VOICE_DOMAIN_IMS,
  RIL_VOICE_DOMAIN_MAX
} RILVOICEDOMAIN;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_VOICE_DOMAIN_3GPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_VOICE_DOMAIN_3GPP2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_VOICE_DOMAIN_IMS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_VOICE_DOMAIN_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_VOICE_DOMAIN_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |