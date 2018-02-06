---
UID: NE:rilapitypes.RILDMCONFIGINFOTYPE
title: RILDMCONFIGINFOTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildmconfiginfotype_2.htm
old-project: netvista
ms.assetid: 86f09204-5f4a-412d-a10b-4692e159ca1b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_DMCV_TYPE_DWORD, rilapitypes/RILDMCONFIGINFOTYPE, RIL_DMCV_TYPE_STRING, rilapitypes/RIL_DMCV_TYPE_BOOLEAN, RIL_DMCV_TYPE_MAX, RILDMCONFIGINFOTYPE, rilapitypes/RIL_DMCV_TYPE_STRING, netvista.rildmconfiginfotype_2, rilapitypes/RIL_DMCV_TYPE_MAX, rilapitypes/RIL_DMCV_TYPE_DWORD, RIL_DMCV_TYPE_BOOLEAN, RILDMCONFIGINFOTYPE enumeration [Network Drivers Starting with Windows Vista]
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
-	RILDMCONFIGINFOTYPE
product: Windows
targetos: Windows
req.typenames: RILDMCONFIGINFOTYPE
req.product: Windows 10 or later.
---

# RILDMCONFIGINFOTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDMCONFIGINFOTYPE { 
  RIL_DMCV_TYPE_BOOLEAN,
  RIL_DMCV_TYPE_DWORD,
  RIL_DMCV_TYPE_STRING,
  RIL_DMCV_TYPE_MAX
} RILDMCONFIGINFOTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DMCV_TYPE_BOOLEAN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DMCV_TYPE_DWORD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DMCV_TYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DMCV_TYPE_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DMCV_TYPE_STRING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |