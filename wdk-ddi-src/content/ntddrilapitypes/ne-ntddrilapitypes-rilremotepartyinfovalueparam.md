---
UID: NE:ntddrilapitypes.RILREMOTEPARTYINFOVALUEPARAM
title: RILREMOTEPARTYINFOVALUEPARAM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfovalueparam.htm
old-project: netvista
ms.assetid: 2e0d5214-d2ec-4cb4-8437-a9f5605ea85a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARAM_RPI_SUBADDRESS, RIL_PARAM_RPI_DESCRIPTION, netvista.rilremotepartyinfovalueparam, ntddrilapitypes/RIL_PARAM_RPI_ADDRESS, RIL_PARAM_RPI_NUM_PRES_IND, ntddrilapitypes/RIL_PARAM_RPI_ID, RIL_PARAM_RPI_ID, RIL_PARAM_RPI_ALL, RILREMOTEPARTYINFOVALUEPARAM enumeration [Network Drivers Starting with Windows Vista], RILREMOTEPARTYINFOVALUEPARAM, ntddrilapitypes/RIL_PARAM_RPI_DESCRIPTION, ntddrilapitypes/RIL_PARAM_RPI_NAME_PRES_IND, ntddrilapitypes/RIL_PARAM_RPI_ALL, ntddrilapitypes/RILREMOTEPARTYINFOVALUEPARAM, RIL_PARAM_RPI_SUBADDRESS, RILREMOTEPARTYINFOPARAM, ntddrilapitypes/RIL_PARAM_RPI_NUM_PRES_IND, RIL_PARAM_RPI_ADDRESS, RIL_PARAM_RPI_NAME_PRES_IND
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
-	RILREMOTEPARTYINFOVALUEPARAM
product: Windows
targetos: Windows
req.typenames: RILREMOTEPARTYINFOVALUEPARAM, RILREMOTEPARTYINFOPARAM
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
| **Header** | ntddrilapitypes.h |