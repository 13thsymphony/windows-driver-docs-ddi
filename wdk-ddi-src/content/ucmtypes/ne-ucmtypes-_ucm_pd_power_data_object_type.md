---
UID: NE:ucmtypes._UCM_PD_POWER_DATA_OBJECT_TYPE
title: "_UCM_PD_POWER_DATA_OBJECT_TYPE"
author: windows-driver-content
description: Defines Power Data Object types.
old-location: buses\ucm_pd_power_data_object_type.htm
old-project: usbref
ms.assetid: FCDD6B04-339D-4BBA-9D19-AE74CCB27666
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_TYPE, UCM_PD_POWER_DATA_OBJECT_TYPE enumeration [Buses], UcmPdPdoTypeBatterySupply, UcmPdPdoTypeFixedSupply, UcmPdPdoTypeVariableSupplyNonBattery, _UCM_PD_POWER_DATA_OBJECT_TYPE, buses.ucm_pd_power_data_object_type, ucmtypes/UCM_PD_POWER_DATA_OBJECT_TYPE, ucmtypes/UcmPdPdoTypeBatterySupply, ucmtypes/UcmPdPdoTypeFixedSupply, ucmtypes/UcmPdPdoTypeVariableSupplyNonBattery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtypes.h
req.include-header: Ucmcx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 2.15
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
-	Ucmtypes.h
api_name:
-	UCM_PD_POWER_DATA_OBJECT_TYPE
product: Windows
targetos: Windows
req.typenames: UCM_PD_POWER_DATA_OBJECT_TYPE
req.product: Windows 10 or later.
---

# _UCM_PD_POWER_DATA_OBJECT_TYPE Enumeration
Defines Power Data Object types.

## Syntax
````
typedef enum _UCM_PD_POWER_DATA_OBJECT_TYPE { 
  UcmPdPdoTypeFixedSupply               = 0,
  UcmPdPdoTypeBatterySupply             = 1,
  UcmPdPdoTypeVariableSupplyNonBattery  = 2
} UCM_PD_POWER_DATA_OBJECT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>UcmPdPdoTypeFixedSupply</td>
                    <td>Indicates the PD data object type is a fixed supply.</td>
                </tr>
            
                <tr>
                    <td>UcmPdPdoTypeBatterySupply</td>
                    <td>Indicates the PD data object type is a battery supply.</td>
                </tr>
            
                <tr>
                    <td>UcmPdPdoTypeVariableSupplyNonBattery</td>
                    <td>Indicates the PD data object type is a non-battery variable supply.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmtypes.h (include Ucmcx.h) |

## See Also

<a href="..\ucmtypes\nf-ucmtypes-ucm_pd_power_data_object_get_type.md">UCM_PD_POWER_DATA_OBJECT_GET_TYPE</a>