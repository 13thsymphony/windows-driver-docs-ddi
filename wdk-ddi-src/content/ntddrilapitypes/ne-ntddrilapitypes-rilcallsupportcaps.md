---
UID: NE:ntddrilapitypes.RILCALLSUPPORTCAPS
title: RILCALLSUPPORTCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallsupportcaps.htm
old-project: netvista
ms.assetid: 1573a1bd-8c47-4fdc-89d1-242e91ff0e47
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_CAPS_CALLSUPPORT_USS, RIL_CAPS_CALLSUPPORT_CNAP, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_CD, RILCALLSUPPORTCAPS, netvista.rilcallsupportcaps, RIL_CAPS_CALLSUPPORT_FM, RIL_CAPS_CALLSUPPORT_MSP, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_ALL, RIL_CAPS_CALLSUPPORT_CD, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_USSD_PHASE2, RIL_CAPS_CALLSUPPORT_ALL, RIL_CAPS_CALLSUPPORT_USSD_PHASE2, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_CUG, RIL_CAPS_CALLSUPPORT_USS, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_MSP, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_EMLPP, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_FM, ntddrilapitypes/RIL_CAPS_CALLSUPPORT_CNAP, RIL_CAPS_CALLSUPPORT_EMLPP, RILCALLSUPPORTCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_CALLSUPPORT_CUG, ntddrilapitypes/RILCALLSUPPORTCAPS
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
-	RILCALLSUPPORTCAPS
product: Windows
targetos: Windows
req.typenames: RILCALLSUPPORTCAPS
---

# RILCALLSUPPORTCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLSUPPORTCAPS { 
  RIL_CAPS_CALLSUPPORT_CD,
  RIL_CAPS_CALLSUPPORT_CNAP,
  RIL_CAPS_CALLSUPPORT_CUG,
  RIL_CAPS_CALLSUPPORT_EMLPP,
  RIL_CAPS_CALLSUPPORT_FM,
  RIL_CAPS_CALLSUPPORT_MSP,
  RIL_CAPS_CALLSUPPORT_USSD_PHASE2,
  RIL_CAPS_CALLSUPPORT_USS,
  RIL_CAPS_CALLSUPPORT_ALL
} RILCALLSUPPORTCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_CCBS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_CD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_CNAP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_CUG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_EMLPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_FM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_MSP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_USS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_CALLSUPPORT_USSD_PHASE2</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |