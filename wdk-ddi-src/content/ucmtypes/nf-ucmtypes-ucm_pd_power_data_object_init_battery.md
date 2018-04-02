---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Battery Supply type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_battery.htm
old-project: usbref
ms.assetid: DA191158-D920-4965-AC2B-7DDA8B541504
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY, UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function [Buses], buses.ucm_pd_power_data_object_init_battery, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
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
-	UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---


# UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY function
Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure as a Battery Supply type Power Data Object.

## Syntax

```
void UCM_PD_POWER_DATA_OBJECT_INIT_BATTERY(
  PUCM_PD_POWER_DATA_OBJECT Pdo
);
```

## Parameters

`Pdo`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>BatterySupplyPdo.Battery</b> member is set to <b>UcmPdPdoTypeBatterySupply</b>.


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