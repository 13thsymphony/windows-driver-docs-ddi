---
UID: NE:ntddrilapitypes.RILTONESIGNALINFOPARAMMASK
title: RILTONESIGNALINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfoparammask.htm
old-project: netvista
ms.assetid: 5ebacb12-4ccd-4e92-ba73-b79c1969eb4f
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.riltonesignalinfoparammask, ntddrilapitypes/RIL_PARAM_TONESIGNAL_All, RILTONESIGNALINFOPARAMMASK, RIL_PARAM_TONESIGNAL_All, ntddrilapitypes/RILTONESIGNALINFOPARAMMASK, ntddrilapitypes/RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, ntddrilapitypes/RIL_PARAM_TONESIGNAL_GPP2TONE, RIL_PARAM_TONESIGNAL_EXECUTOR, ntddrilapitypes/RIL_PARAM_TONESIGNAL_EXECUTOR, RIL_PARAM_TONESIGNAL_GPP2ISDNALERTING, RIL_PARAM_TONESIGNAL_GPP2TONE, RILTONESIGNALINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILTONESIGNALINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFOPARAMMASK
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
| **Header** | ntddrilapitypes.h |