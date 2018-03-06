---
UID: NE:rilapitypes.RILCALLINFOFLAGS
title: RILCALLINFOFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfoflags_2.htm
old-project: netvista
ms.assetid: 7b701e86-ee0b-4a46-a6bf-4a4fe18c371f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILCALLINFOFLAGS, RILCALLINFOFLAGS enumeration [Network Drivers Starting with Windows Vista], RILCALLINFO_FLAG_ALIENCALL, RILCALLINFO_FLAG_EMERGENCYCALL, netvista.rilcallinfoflags_2, rilapitypes/RILCALLINFOFLAGS, rilapitypes/RILCALLINFO_FLAG_ALIENCALL, rilapitypes/RILCALLINFO_FLAG_EMERGENCYCALL
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
-	RILCALLINFOFLAGS
product: Windows
targetos: Windows
req.typenames: RILCALLINFOFLAGS
req.product: Windows 10 or later.
---

# RILCALLINFOFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLINFOFLAGS { 
  RILCALLINFO_FLAG_ALIENCALL,
  RILCALLINFO_FLAG_EMERGENCYCALL
} RILCALLINFOFLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>RILCALLINFO_FLAG_ALIENCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RILCALLINFO_FLAG_EMERGENCYCALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RILCALLINFO_FLAG_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |