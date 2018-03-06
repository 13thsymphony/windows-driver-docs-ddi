---
UID: NE:rilapitypes.RILSMSSUPPORTCAPS
title: RILSMSSUPPORTCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmssupportcaps_2.htm
old-project: netvista
ms.assetid: 38dac27d-1415-44bb-8dd6-2a6b6bd2a774
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILSMSSUPPORTCAPS, RILSMSSUPPORTCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_SMSSUPPORT_16BITREFERENCENUMBER, RIL_CAPS_SMSSUPPORT_ALL, netvista.rilsmssupportcaps_2, rilapitypes/RILSMSSUPPORTCAPS, rilapitypes/RIL_CAPS_SMSSUPPORT_16BITREFERENCENUMBER, rilapitypes/RIL_CAPS_SMSSUPPORT_ALL
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
-	RILSMSSUPPORTCAPS
product: Windows
targetos: Windows
req.typenames: RILSMSSUPPORTCAPS
req.product: Windows 10 or later.
---

# RILSMSSUPPORTCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSMSSUPPORTCAPS { 
  RIL_CAPS_SMSSUPPORT_16BITREFERENCENUMBER,
  RIL_CAPS_SMSSUPPORT_ALL
} RILSMSSUPPORTCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_SMSSUPPORT_16BITREFERENCENUMBER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SMSSUPPORT_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SMSSUPPORT_PERSISTLINK</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |