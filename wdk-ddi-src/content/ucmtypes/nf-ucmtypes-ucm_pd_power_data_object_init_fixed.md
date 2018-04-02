---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
title: UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function
author: windows-driver-content
description: Initializes a to the UCM_PD_POWER_DATA_OBJECT for a Fixed Supply type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_fixed.htm
old-project: usbref
ms.assetid: AC51EA77-7F5B-42DE-B366-7BCE46AA5097
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCM_PD_POWER_DATA_OBJECT_INIT_FIXED, UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function [Buses], buses.ucm_pd_power_data_object_init_fixed, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
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
-	UCM_PD_POWER_DATA_OBJECT_INIT_FIXED
product:
- Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---


# UCM_PD_POWER_DATA_OBJECT_INIT_FIXED function
Initializes a to the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> for a Fixed Supply type Power Data Object.

## Syntax

```
void UCM_PD_POWER_DATA_OBJECT_INIT_FIXED(
  PUCM_PD_POWER_DATA_OBJECT Pdo
);
```

## Parameters

`Pdo`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187935">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>FixedSupplyPdo.FixedSupply</b> member is set to <b>UcmPdPdoTypeFixedSupply</b>.


## Return Value

This function does not return a value.

## Remarks

For different types of Power Data Objects, see the power delivery specification. 

This function initializes the structure and sets Power Data Object as a Fixed Supply type. The client driver must set the remaining members with values relevant to the specific object type.

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