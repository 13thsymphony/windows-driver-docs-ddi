---
UID: NE:rilapitypes.RILTONESIGNALINFOPARAMMASK
title: RILTONESIGNALINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfoparammask_2.htm
old-project: netvista
ms.assetid: 1eeca3ef-6e1d-486f-b700-5ab8718a9285
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_TONESIGNAL_EXECUTOR, RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, netvista.riltonesignalinfoparammask_2, rilapitypes/RIL_PARAM_TONESIGNAL_All, rilapitypes/RIL_PARAM_TONESIGNAL_GPP2TONE, RIL_PARAM_TONESIGNAL_All, RILTONESIGNALINFOPARAMMASK, rilapitypes/RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, RIL_PARAM_TONESIGNAL_EXECUTOR, RILTONESIGNALINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILTONESIGNALINFOPARAMMASK, RIL_PARAM_TONESIGNAL_GPP2TONE
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
-	RILTONESIGNALINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILTONESIGNALINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILTONESIGNALINFOPARAMMASK { 
  RIL_PARAM_TONESIGNAL_GPP2TONE,
  RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING,
  RIL_PARAM_TONESIGNAL_EXECUTOR,
  RIL_PARAM_TONESIGNAL_All
} RILTONESIGNALINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_TONESIGNAL_All</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_TONESIGNAL_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_TONESIGNAL_GPP2TONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_TONESIGNAL_GPPTONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |