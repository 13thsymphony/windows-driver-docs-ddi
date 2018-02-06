---
UID: NE:ntddrilapitypes.RILHIDECONNECTEDIDSETTINGSPARAMMASK
title: RILHIDECONNECTEDIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettingsparammask.htm
old-project: netvista
ms.assetid: 24d14690-4c74-46d2-ad57-3e21edb00509
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_HCIDS_PROVISIONING, ntddrilapitypes/RILHIDECONNECTEDIDSETTINGSPARAMMASK, ntddrilapitypes/RIL_PARAM_HCIDS_PROVISIONING, netvista.rilhideconnectedidsettingsparammask, RILHIDECONNECTEDIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RILHIDECONNECTEDIDSETTINGSPARAMMASK, RIL_PARAM_HCIDS_ALL, ntddrilapitypes/RIL_PARAM_HCIDS_ALL, ntddrilapitypes/RIL_PARAM_HCIDS_STATUS, RIL_PARAM_HCIDS_STATUS
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
-	RILHIDECONNECTEDIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILHIDECONNECTEDIDSETTINGSPARAMMASK
---

# RILHIDECONNECTEDIDSETTINGSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILHIDECONNECTEDIDSETTINGSPARAMMASK { 
  RIL_PARAM_HCIDS_STATUS,
  RIL_PARAM_HCIDS_PROVISIONING,
  RIL_PARAM_HCIDS_ALL
} RILHIDECONNECTEDIDSETTINGSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_HCIDS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_HCIDS_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_HCIDS_PROVISIONING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_HCIDS_STATUS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |