---
UID: NE:ntddrilapitypes.RILDIALEDIDSETTINGSPARAMMASK
title: RILDIALEDIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialedidsettingsparammask.htm
old-project: netvista
ms.assetid: 8883e9fc-9f2a-4367-ae2d-30260f2d2de6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILDIALEDIDSETTINGSPARAMMASK, RILDIALEDIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_DIDS_ALL, RIL_PARAM_DIDS_PROVISIONING, RIL_PARAM_DIDS_STATUS, netvista.rildialedidsettingsparammask, ntddrilapitypes/RILDIALEDIDSETTINGSPARAMMASK, ntddrilapitypes/RIL_PARAM_DIDS_ALL, ntddrilapitypes/RIL_PARAM_DIDS_PROVISIONING, ntddrilapitypes/RIL_PARAM_DIDS_STATUS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILDIALEDIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDIALEDIDSETTINGSPARAMMASK
---

# RILDIALEDIDSETTINGSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDIALEDIDSETTINGSPARAMMASK { 
  RIL_PARAM_DIDS_PROVISIONING,
  RIL_PARAM_DIDS_STATUS,
  RIL_PARAM_DIDS_ALL
} RILDIALEDIDSETTINGSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_DIDS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DIDS_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DIDS_PROVISIONING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_DIDS_STATUS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |