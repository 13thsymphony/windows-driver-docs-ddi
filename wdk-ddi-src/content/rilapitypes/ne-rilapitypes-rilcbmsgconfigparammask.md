---
UID: NE:rilapitypes.RILCBMSGCONFIGPARAMMASK
title: RILCBMSGCONFIGPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbmsgconfigparammask_2.htm
old-project: netvista
ms.assetid: ec2a26a0-4325-41d9-a6b4-5b9c2f22dd4e
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_PARAM_CBMC_CDMASIZE, RIL_PARAM_CBMC_GWLINFO, rilapitypes/RIL_PARAM_CBMC_GWLINFO, RILCBMSGCONFIGPARAMMASK enumeration [Network Drivers Starting with Windows Vista], netvista.rilcbmsgconfigparammask_2, rilapitypes/RILCBMSGCONFIGPARAMMASK, rilapitypes/RIL_PARAM_CBMC_CDMASIZE, RIL_PARAM_CBMC_CDMAINFO, rilapitypes/RIL_PARAM_CBMC_ALL, rilapitypes/RIL_PARAM_CBMC_CDMAINFO, RILCBMSGCONFIGPARAMMASK, RIL_PARAM_CBMC_ALL
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
-	RILCBMSGCONFIGPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCBMSGCONFIGPARAMMASK
req.product: Windows 10 or later.
---

# RILCBMSGCONFIGPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCBMSGCONFIGPARAMMASK { 
  RIL_PARAM_CBMC_GWLINFO,
  RIL_PARAM_CBMC_CDMASIZE,
  RIL_PARAM_CBMC_CDMAINFO,
  RIL_PARAM_CBMC_ALL
} RILCBMSGCONFIGPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_CBMC_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CBMC_CDMAINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CBMC_CDMASIZE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CBMC_GWLINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_CBMC_GWLSIZE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |