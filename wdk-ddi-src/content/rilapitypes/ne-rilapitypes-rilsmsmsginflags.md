---
UID: NE:rilapitypes.RILSMSMSGINFLAGS
title: RILSMSMSGINFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsmsginflags_2.htm
old-project: netvista
ms.assetid: 83842f98-6ec5-443a-ad48-492a487a6dae
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rilapitypes/RILSMSMSGINFLAGS, rilapitypes/RIL_SMSMSGIN_ALL, RIL_SMSMSGIN_ALL, RILSMSMSGINFLAGS enumeration [Network Drivers Starting with Windows Vista], RIL_SMSMSGIN_IMS, RILSMSMSGINFLAGS, netvista.rilsmsmsginflags_2, rilapitypes/RIL_SMSMSGIN_IMS
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
                    <td>RIL_SMSMSGIN_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSMSGIN_IMS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSMSGIN_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |