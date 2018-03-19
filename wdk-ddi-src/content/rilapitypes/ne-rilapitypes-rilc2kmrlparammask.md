---
UID: NE:rilapitypes.RILC2KMRLPARAMMASK
title: RILC2KMRLPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilc2kmrlparammask_2.htm
old-project: netvista
ms.assetid: 267cd226-c1a9-4636-9709-01e3cc947349
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILC2KMRLPARAMMASK, RILC2KMRLPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_C2KMRL_BASELAT, RIL_PARAM_C2KMRL_BASELONG, RIL_PARAM_C2KMRL_BSID, RIL_PARAM_C2KMRL_GPSSECONDS, RIL_PARAM_C2KMRL_NID, RIL_PARAM_C2KMRL_PILOTSTRENGTH, RIL_PARAM_C2KMRL_REFPN, RIL_PARAM_C2KMRL_SID, RIL_PARAM_C2KRML_ALL, netvista.rilc2kmrlparammask_2, rilapitypes/RILC2KMRLPARAMMASK, rilapitypes/RIL_PARAM_C2KMRL_BASELAT, rilapitypes/RIL_PARAM_C2KMRL_BASELONG, rilapitypes/RIL_PARAM_C2KMRL_BSID, rilapitypes/RIL_PARAM_C2KMRL_GPSSECONDS, rilapitypes/RIL_PARAM_C2KMRL_NID, rilapitypes/RIL_PARAM_C2KMRL_PILOTSTRENGTH, rilapitypes/RIL_PARAM_C2KMRL_REFPN, rilapitypes/RIL_PARAM_C2KMRL_SID, rilapitypes/RIL_PARAM_C2KRML_ALL
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
-	RILC2KMRLPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILC2KMRLPARAMMASK
req.product: Windows 10 or later.
---

# RILC2KMRLPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILC2KMRLPARAMMASK { 
  RIL_PARAM_C2KMRL_NID,
  RIL_PARAM_C2KMRL_SID,
  RIL_PARAM_C2KMRL_BSID,
  RIL_PARAM_C2KMRL_BASELAT,
  RIL_PARAM_C2KMRL_BASELONG,
  RIL_PARAM_C2KMRL_REFPN,
  RIL_PARAM_C2KMRL_GPSSECONDS,
  RIL_PARAM_C2KMRL_PILOTSTRENGTH,
  RIL_PARAM_C2KRML_ALL
} RILC2KMRLPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_SERVING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_NID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_SID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_BSID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_BASELAT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_BASELONG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_REFPN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_GPSSECONDS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KMRL_PILOTSTRENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_C2KRML_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |