---
UID: NE:rilapitypes.RILREMOTEPARTYINFOVALUEPARAM
title: RILREMOTEPARTYINFOVALUEPARAM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfovalueparam_2.htm
old-project: netvista
ms.assetid: eeea39eb-898a-47fe-befe-39c95dd1fc90
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilremotepartyinfovalueparam_2, rilapitypes/RILREMOTEPARTYINFOVALUEPARAM, RIL_PARAM_RPI_DESCRIPTION, rilapitypes/RIL_PARAM_RPI_ADDRESS, rilapitypes/RIL_PARAM_RPI_ALL, RIL_PARAM_RPI_NUM_PRES_IND, rilapitypes/RIL_PARAM_RPI_ID, RIL_PARAM_RPI_ALL, RIL_PARAM_RPI_ID, RILREMOTEPARTYINFOVALUEPARAM enumeration [Network Drivers Starting with Windows Vista], RILREMOTEPARTYINFOVALUEPARAM, RILREMOTEPARTYINFOPARAM, rilapitypes/RIL_PARAM_RPI_NAME_PRES_IND, RIL_PARAM_RPI_SUBADDRESS, rilapitypes/RIL_PARAM_RPI_SUBADDRESS, rilapitypes/RIL_PARAM_RPI_NUM_PRES_IND, RIL_PARAM_RPI_ADDRESS, RIL_PARAM_RPI_NAME_PRES_IND, rilapitypes/RIL_PARAM_RPI_DESCRIPTION
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
-	RILREMOTEPARTYINFOVALUEPARAM
product: Windows
targetos: Windows
req.typenames: RILREMOTEPARTYINFOVALUEPARAM, RILREMOTEPARTYINFOPARAM
req.product: Windows 10 or later.
---

# RILREMOTEPARTYINFOVALUEPARAM Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILREMOTEPARTYINFOVALUEPARAM { 
  RIL_PARAM_RPI_ADDRESS,
  RIL_PARAM_RPI_SUBADDRESS,
  RIL_PARAM_RPI_DESCRIPTION,
  RIL_PARAM_RPI_NUM_PRES_IND,
  RIL_PARAM_RPI_NAME_PRES_IND,
  RIL_PARAM_RPI_ID,
  RIL_PARAM_RPI_ALL
} RILREMOTEPARTYINFOVALUEPARAM;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_RPI_ADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_DESCRIPTION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_NAME_PRES_IND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_NUM_PRES_IND</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_RPI_SUBADDRESS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |