---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Variable Supply Non Battery type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_variable_non_battery.htm
old-project: usbref
ms.assetid: BBC8975A-E5B1-4137-83D8-891075A8F4D0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY, UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function [Buses], buses.ucm_pd_power_data_object_init_variable_non_battery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
-	UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---


# UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function
Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure as a Variable Supply Non Battery type Power Data Object.

## Syntax

```
void UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY(
  PUCM_PD_POWER_DATA_OBJECT Pdo
);
```

## Parameters

`Pdo`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>VariableSupplyNonBatteryPdo.VariableSupportNonBattery</b> member is set to <b>UcmPdPdoTypeVariableSupplyNonBattery</b>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmtypes.h (include Ucmcx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a>