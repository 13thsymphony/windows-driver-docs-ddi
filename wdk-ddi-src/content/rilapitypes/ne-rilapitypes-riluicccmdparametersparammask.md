---
UID: NE:rilapitypes.RILUICCCMDPARAMETERSPARAMMASK
title: RILUICCCMDPARAMETERSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicccmdparametersparammask_2.htm
old-project: netvista
ms.assetid: 56b6b8e6-529d-4480-bce8-ae94d09d1643
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILUICCCMDPARAMETERSPARAMMASK, RILUICCCMDPARAMETERSPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_SCP_ALL, RIL_PARAM_SCP_PARAM1, RIL_PARAM_SCP_PARAM2, RIL_PARAM_SCP_PARAM3, netvista.riluicccmdparametersparammask_2, rilapitypes/RILUICCCMDPARAMETERSPARAMMASK, rilapitypes/RIL_PARAM_SCP_ALL, rilapitypes/RIL_PARAM_SCP_PARAM1, rilapitypes/RIL_PARAM_SCP_PARAM2, rilapitypes/RIL_PARAM_SCP_PARAM3
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
-	RILUICCCMDPARAMETERSPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUICCCMDPARAMETERSPARAMMASK
req.product: Windows 10 or later.
---

# RILUICCCMDPARAMETERSPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUICCCMDPARAMETERSPARAMMASK { 
  RIL_PARAM_SCP_PARAM1,
  RIL_PARAM_SCP_PARAM2,
  RIL_PARAM_SCP_PARAM3,
  RIL_PARAM_SCP_ALL
} RILUICCCMDPARAMETERSPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_SCP_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SCP_FILEPATH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SCP_PARAM1</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SCP_PARAM2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_SCP_PARAM3</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |