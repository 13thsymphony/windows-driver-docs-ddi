---
UID: NE:rilapitypes.RILSMSMSGINFLAGS
title: RILSMSMSGINFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmsginflags.htm
old-project: netvista
ms.assetid: aaa7967a-dfbc-4c4c-a309-095628fae6c0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSMSMSGINFLAGS, RILSMSMSGINFLAGS enumeration [Network Drivers Starting with Windows Vista], RIL_SMSMSGIN_ALL, RIL_SMSMSGIN_IMS, netvista.rilsmsmsginflags, ntddrilapitypes/RILSMSMSGINFLAGS, ntddrilapitypes/RIL_SMSMSGIN_ALL, ntddrilapitypes/RIL_SMSMSGIN_IMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILSMSMSGINFLAGS
product: Windows
targetos: Windows
req.typenames: RILSMSMSGINFLAGS
req.product: Windows 10 or later.
---

# RILSMSMSGINFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSMSMSGINFLAGS { 
  RIL_SMSMSGIN_IMS,
  RIL_SMSMSGIN_ALL
} RILSMSMSGINFLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SMSMSGIN_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSMSGIN_IMS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSMSGIN_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |