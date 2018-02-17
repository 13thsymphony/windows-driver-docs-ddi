---
UID: NE:rilapitypes.RILCALLSUPPORTCAPS
title: RILCALLSUPPORTCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallsupportcaps_2.htm
old-project: netvista
ms.assetid: f51ab865-8862-4ed2-830e-ecbef4c9c74e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CAPS_CALLSUPPORT_USSD_PHASE2, RIL_CAPS_CALLSUPPORT_CNAP, rilapitypes/RIL_CAPS_CALLSUPPORT_USS, RIL_CAPS_CALLSUPPORT_USS, rilapitypes/RILCALLSUPPORTCAPS, rilapitypes/RIL_CAPS_CALLSUPPORT_MSP, RIL_CAPS_CALLSUPPORT_CD, RILCALLSUPPORTCAPS enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_CAPS_CALLSUPPORT_CD, netvista.rilcallsupportcaps_2, rilapitypes/RIL_CAPS_CALLSUPPORT_CUG, rilapitypes/RIL_CAPS_CALLSUPPORT_CNAP, rilapitypes/RIL_CAPS_CALLSUPPORT_ALL, RIL_CAPS_CALLSUPPORT_CUG, RIL_CAPS_CALLSUPPORT_MSP, rilapitypes/RIL_CAPS_CALLSUPPORT_USSD_PHASE2, RILCALLSUPPORTCAPS, RIL_CAPS_CALLSUPPORT_EMLPP, rilapitypes/RIL_CAPS_CALLSUPPORT_FM, RIL_CAPS_CALLSUPPORT_ALL, rilapitypes/RIL_CAPS_CALLSUPPORT_EMLPP, RIL_CAPS_CALLSUPPORT_FM
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
-	RILCALLSUPPORTCAPS
product: Windows
targetos: Windows
req.typenames: RILCALLSUPPORTCAPS
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |