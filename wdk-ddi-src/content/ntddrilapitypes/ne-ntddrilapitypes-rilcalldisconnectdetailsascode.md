---
UID: NE:ntddrilapitypes.RILCALLDISCONNECTDETAILSASCODE
title: RILCALLDISCONNECTDETAILSASCODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalldisconnectdetailsascode.htm
old-project: netvista
ms.assetid: 01b311e9-252e-49eb-bf63-d16e4fa92231
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILCALLDISCONNECTDETAILSASCODE, RILCALLDISCONNECTDETAILSASCODE enumeration [Network Drivers Starting with Windows Vista], RIL_CD_L2, RIL_CD_L3, RIL_CD_LAYER_MAX, netvista.rilcalldisconnectdetailsascode, ntddrilapitypes/RILCALLDISCONNECTDETAILSASCODE, ntddrilapitypes/RIL_CD_L2, ntddrilapitypes/RIL_CD_L3, ntddrilapitypes/RIL_CD_LAYER_MAX
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
-	RILCALLDISCONNECTDETAILSASCODE
product: Windows
targetos: Windows
req.typenames: RILCALLDISCONNECTDETAILSASCODE
---

# RILCALLDISCONNECTDETAILSASCODE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILCALLDISCONNECTDETAILSASCODE {
  RIL_CD_PHYSICAL_LAYER  ,
  RIL_CD_L2              ,
  RIL_CD_L3              ,
  RIL_CD_LAYER_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_CD_PHYSICAL_LAYER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_L2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_L3</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CD_LAYER_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |