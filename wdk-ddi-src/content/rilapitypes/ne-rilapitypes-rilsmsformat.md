---
UID: NE:rilapitypes.RILSMSFORMAT
title: RILSMSFORMAT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsformat_2.htm
old-project: netvista
ms.assetid: c2e115d7-810f-4415-9177-6bad7bbc0f5b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSMSFORMAT, RILSMSFORMAT enumeration [Network Drivers Starting with Windows Vista], RIL_SMSFORMAT_3GPP, RIL_SMSFORMAT_3GPP2, RIL_SMSFORMAT_MAX, netvista.rilsmsformat_2, rilapitypes/RILSMSFORMAT, rilapitypes/RIL_SMSFORMAT_3GPP, rilapitypes/RIL_SMSFORMAT_3GPP2, rilapitypes/RIL_SMSFORMAT_MAX
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILSMSFORMAT
product: Windows
targetos: Windows
req.typenames: RILSMSFORMAT
req.product: Windows 10 or later.
---

# RILSMSFORMAT Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSMSFORMAT { 
  RIL_SMSFORMAT_3GPP,
  RIL_SMSFORMAT_3GPP2,
  RIL_SMSFORMAT_MAX
} RILSMSFORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SMSFORMAT_3GPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSFORMAT_3GPP2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSFORMAT_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSFORMAT_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |