---
UID: NE:rilapitypes.RILDIALPARAMSOPTIONS
title: RILDIALPARAMSOPTIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialparamsoptions.htm
old-project: netvista
ms.assetid: 78fef8f7-e6cd-4da6-9c2a-2eaf1da6339b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILDIALPARAMSOPTIONS, RILDIALPARAMSOPTIONS enumeration [Network Drivers Starting with Windows Vista], RIL_DIALOPT_ALL, RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, RIL_DIALOPT_PRESENTID, RIL_DIALOPT_RESTRICTID, RIL_DIALOPT_RTTFULL, netvista.rildialparamsoptions, ntddrilapitypes/RILDIALPARAMSOPTIONS, ntddrilapitypes/RIL_DIALOPT_ALL, ntddrilapitypes/RIL_DIALOPT_ANYEXECUTORFOREMERGENCY, ntddrilapitypes/RIL_DIALOPT_PRESENTID, ntddrilapitypes/RIL_DIALOPT_RESTRICTID, ntddrilapitypes/RIL_DIALOPT_RTTFULL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
-	RILDIALPARAMSOPTIONS
product: Windows
targetos: Windows
req.typenames: RILDIALPARAMSOPTIONS
req.product: Windows 10 or later.
---

# RILDIALPARAMSOPTIONS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDIALPARAMSOPTIONS { 
  RIL_DIALOPT_RESTRICTID,
  RIL_DIALOPT_PRESENTID,
  RIL_DIALOPT_ANYEXECUTORFOREMERGENCY,
  RIL_DIALOPT_RTTFULL,
  RIL_DIALOPT_ALL
} RILDIALPARAMSOPTIONS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DIALOPT_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DIALOPT_RESTRICTID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DIALOPT_PRESENTID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DIALOPT_ANYEXECUTORFOREMERGENCY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DIALOPT_RTTFULL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DIALOPT_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |