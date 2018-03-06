---
UID: NE:rilapitypes.RILMSGOUTSUBMITVPFORMAT
title: RILMSGOUTSUBMITVPFORMAT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgoutsubmitvpformat_2.htm
old-project: netvista
ms.assetid: aa383bc9-935d-4883-929d-4ea58a1bf2c9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILMSGOUTSUBMITVPFORMAT, RILMSGOUTSUBMITVPFORMAT enumeration [Network Drivers Starting with Windows Vista], RIL_MSGVP_ABSOLUTE, RIL_MSGVP_ENHANCED, RIL_MSGVP_MAX, RIL_MSGVP_RELATIVE, netvista.rilmsgoutsubmitvpformat_2, rilapitypes/RILMSGOUTSUBMITVPFORMAT, rilapitypes/RIL_MSGVP_ABSOLUTE, rilapitypes/RIL_MSGVP_ENHANCED, rilapitypes/RIL_MSGVP_MAX, rilapitypes/RIL_MSGVP_RELATIVE
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
-	RILMSGOUTSUBMITVPFORMAT
product: Windows
targetos: Windows
req.typenames: RILMSGOUTSUBMITVPFORMAT
req.product: Windows 10 or later.
---

# RILMSGOUTSUBMITVPFORMAT Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGOUTSUBMITVPFORMAT { 
  RIL_MSGVP_RELATIVE,
  RIL_MSGVP_ENHANCED,
  RIL_MSGVP_ABSOLUTE,
  RIL_MSGVP_MAX
} RILMSGOUTSUBMITVPFORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGVP_ABSOLUTE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGVP_ENHANCED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGVP_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGVP_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGVP_RELATIVE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |