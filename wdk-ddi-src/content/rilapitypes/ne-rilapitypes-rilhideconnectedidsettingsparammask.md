---
UID: NE:rilapitypes.RILHIDECONNECTEDIDSETTINGSPARAMMASK
title: RILHIDECONNECTEDIDSETTINGSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilhideconnectedidsettingsparammask_2.htm
old-project: netvista
ms.assetid: 7977898a-9f45-4db5-9fe3-3702f6bc9124
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILHIDECONNECTEDIDSETTINGSPARAMMASK, RILHIDECONNECTEDIDSETTINGSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_HCIDS_ALL, RIL_PARAM_HCIDS_PROVISIONING, RIL_PARAM_HCIDS_STATUS, netvista.rilhideconnectedidsettingsparammask_2, rilapitypes/RILHIDECONNECTEDIDSETTINGSPARAMMASK, rilapitypes/RIL_PARAM_HCIDS_ALL, rilapitypes/RIL_PARAM_HCIDS_PROVISIONING, rilapitypes/RIL_PARAM_HCIDS_STATUS
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
-	RILHIDECONNECTEDIDSETTINGSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILHIDECONNECTEDIDSETTINGSPARAMMASK
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |