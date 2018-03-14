---
UID: NE:ntddrilapitypes.RILEMERGENCYMODECONTROLPARAMSCONTROL
title: RILEMERGENCYMODECONTROLPARAMSCONTROL
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencymodecontrolparamscontrol.htm
old-project: netvista
ms.assetid: ac5a2ae3-3fdc-463f-96df-22b441e38724
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILEMERGENCYMODECONTROLPARAMSCONTROL, RILEMERGENCYMODECONTROLPARAMSCONTROL enumeration [Network Drivers Starting with Windows Vista], RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE, RIL_EMC_MAX, RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE, netvista.rilemergencymodecontrolparamscontrol, ntddrilapitypes/RILEMERGENCYMODECONTROLPARAMSCONTROL, ntddrilapitypes/RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE, ntddrilapitypes/RIL_EMC_MAX, ntddrilapitypes/RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE
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
-	RILEMERGENCYMODECONTROLPARAMSCONTROL
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYMODECONTROLPARAMSCONTROL
---

# RILEMERGENCYMODECONTROLPARAMSCONTROL Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEMERGENCYMODECONTROLPARAMSCONTROL { 
  RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE,
  RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE,
  RIL_EMC_MAX
} RILEMERGENCYMODECONTROLPARAMSCONTROL;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_EMC_ALL_MODEMS_ARE_IN_NORMAL_MODE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EMC_EXIT_CDMA_ECBM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EMC_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EMC_OTHER_MODEM_IN_EMERGECY_MODE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |