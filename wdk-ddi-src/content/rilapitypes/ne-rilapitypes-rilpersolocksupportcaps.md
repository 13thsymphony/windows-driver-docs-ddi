---
UID: NE:rilapitypes.RILPERSOLOCKSUPPORTCAPS
title: RILPERSOLOCKSUPPORTCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersolocksupportcaps_2.htm
old-project: netvista
ms.assetid: 630f48cc-2236-48ec-a62a-cdafa31a3afd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP_USIM, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE2, RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE1, RIL_CAPS_PERSOFEATURE_3GPP2_SP, RILPERSOLOCKSUPPORTCAPS, RIL_CAPS_PERSOFEATURE_3GPP2_UIM, netvista.rilpersolocksupportcaps_2, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_HRPD, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP_SP, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP_NETSUB, RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE2, RIL_CAPS_PERSOFEATURE_ALL, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_CORP, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_UIM, rilapitypes/RIL_CAPS_PERSOFEATURE_ALL, RIL_CAPS_PERSOFEATURE_3GPP2_HRPD, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE1, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP2_SP, RIL_CAPS_PERSOFEATURE_3GPP_NETSUB, rilapitypes/RIL_CAPS_PERSOFEATURE_3GPP_CORP, RILPERSOLOCKSUPPORTCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_PERSOFEATURE_3GPP_USIM, RIL_CAPS_PERSOFEATURE_3GPP_CORP, RIL_CAPS_PERSOFEATURE_3GPP_SP, RIL_CAPS_PERSOFEATURE_3GPP2_CORP, rilapitypes/RILPERSOLOCKSUPPORTCAPS
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
-	RILPERSOLOCKSUPPORTCAPS
product: Windows
targetos: Windows
req.typenames: RILPERSOLOCKSUPPORTCAPS
req.product: Windows 10 or later.
---

# RILPERSOLOCKSUPPORTCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPERSOLOCKSUPPORTCAPS { 
  RIL_CAPS_PERSOFEATURE_3GPP_NETSUB,
  RIL_CAPS_PERSOFEATURE_3GPP_SP,
  RIL_CAPS_PERSOFEATURE_3GPP_CORP,
  RIL_CAPS_PERSOFEATURE_3GPP_USIM,
  RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE1,
  RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE2,
  RIL_CAPS_PERSOFEATURE_3GPP2_HRPD,
  RIL_CAPS_PERSOFEATURE_3GPP2_SP,
  RIL_CAPS_PERSOFEATURE_3GPP2_CORP,
  RIL_CAPS_PERSOFEATURE_3GPP2_UIM,
  RIL_CAPS_PERSOFEATURE_ALL
} RILPERSOLOCKSUPPORTCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP_CORP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP_NET</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP_NETSUB</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP_SP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP_USIM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_CORP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_HRPD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_NETTYPE2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_SP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_3GPP2_UIM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PERSOFEATURE_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |