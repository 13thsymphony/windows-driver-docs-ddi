---
UID: NE:rilapitypes.RILSENDMSGOPTIONS
title: RILSENDMSGOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgoptions_2.htm
old-project: netvista
ms.assetid: 84d13b43-06c4-4454-9853-80b1fe65d29d
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSENDMSGOPTIONS, RILSENDMSGOPTIONS enumeration [Network Drivers Starting with Windows Vista], RIL_SENDOPT_IMS, RIL_SENDOPT_PERSISTLINK, netvista.rilsendmsgoptions_2, rilapitypes/RILSENDMSGOPTIONS, rilapitypes/RIL_SENDOPT_IMS, rilapitypes/RIL_SENDOPT_PERSISTLINK
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
-	RILSENDMSGOPTIONS
product: Windows
targetos: Windows
req.typenames: RILSENDMSGOPTIONS
req.product: Windows 10 or later.
---

# RILSENDMSGOPTIONS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSENDMSGOPTIONS { 
  RIL_SENDOPT_PERSISTLINK,
  RIL_SENDOPT_IMS
} RILSENDMSGOPTIONS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SENDOPT_IMS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SENDOPT_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SENDOPT_PERSISTLINK</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |