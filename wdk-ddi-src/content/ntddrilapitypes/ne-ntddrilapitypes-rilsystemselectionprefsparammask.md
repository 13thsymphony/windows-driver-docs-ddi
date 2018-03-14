---
UID: NE:ntddrilapitypes.RILSYSTEMSELECTIONPREFSPARAMMASK
title: RILSYSTEMSELECTIONPREFSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefsparammask.htm
old-project: netvista
ms.assetid: 69560c05-8a54-4a67-a441-2b3c2ec4c332
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSYSTEMSELECTIONPREFSPARAMMASK, RILSYSTEMSELECTIONPREFSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SSP_ACQUISITIONORDER, RIL_PARAM_SSP_ACQUISITIONORDERSIZE, RIL_PARAM_SSP_ALL, RIL_PARAM_SSP_MODE, RIL_PARAM_SSP_PLMNINFO, RIL_PARAM_SSP_ROAMINGMODE, RIL_PARAM_SSP_SYSTEMTYPES, netvista.rilsystemselectionprefsparammask, ntddrilapitypes/RILSYSTEMSELECTIONPREFSPARAMMASK, ntddrilapitypes/RIL_PARAM_SSP_ACQUISITIONORDER, ntddrilapitypes/RIL_PARAM_SSP_ACQUISITIONORDERSIZE, ntddrilapitypes/RIL_PARAM_SSP_ALL, ntddrilapitypes/RIL_PARAM_SSP_MODE, ntddrilapitypes/RIL_PARAM_SSP_PLMNINFO, ntddrilapitypes/RIL_PARAM_SSP_ROAMINGMODE, ntddrilapitypes/RIL_PARAM_SSP_SYSTEMTYPES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	RILSYSTEMSELECTIONPREFSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFSPARAMMASK
---

# RILSYSTEMSELECTIONPREFSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSYSTEMSELECTIONPREFSPARAMMASK { 
  RIL_PARAM_SSP_SYSTEMTYPES,
  RIL_PARAM_SSP_MODE,
  RIL_PARAM_SSP_PLMNINFO,
  RIL_PARAM_SSP_ROAMINGMODE,
  RIL_PARAM_SSP_ACQUISITIONORDERSIZE,
  RIL_PARAM_SSP_ACQUISITIONORDER,
  RIL_PARAM_SSP_ALL
} RILSYSTEMSELECTIONPREFSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SSP_ACQUISITIONORDER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_ACQUISITIONORDERSIZE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_MODE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_PLMNINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_ROAMINGMODE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SSP_SYSTEMTYPES</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |