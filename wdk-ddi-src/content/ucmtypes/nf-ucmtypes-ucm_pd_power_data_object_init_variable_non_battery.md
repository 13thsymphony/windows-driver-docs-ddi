---
UID: NF:ucmtypes.UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
title: UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function
author: windows-driver-content
description: Initializes a UCM_PD_POWER_DATA_OBJECT structure as a Variable Supply Non Battery type Power Data Object.
old-location: buses\ucm_pd_power_data_object_init_variable_non_battery.htm
old-project: usbref
ms.assetid: BBC8975A-E5B1-4137-83D8-891075A8F4D0
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ucm_pd_power_data_object_init_variable_non_battery, UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function [Buses], UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY, ucmtypes/UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmtypes.h
apiname:
-	UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY
product: Windows
targetos: Windows
req.typenames: UCM_TYPEC_PARTNER
req.product: Windows 10 or later.
---


# UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function
Initializes a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure as a Variable Supply Non Battery type Power Data Object.

## Syntax

````
FORCEINLINE void UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY(
  _Out_ PUCM_PD_POWER_DATA_OBJECT Pdo
);
````

## Parameters

`Pdo`

A pointer to a <a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a> structure in which the <b>VariableSupplyNonBatteryPdo.VariableSupportNonBattery</b> member is set to <b>UcmPdPdoTypeVariableSupplyNonBattery</b>.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmtypes.h (include Ucmcx.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\ucmtypes\ns-ucmtypes-_ucm_pd_power_data_object.md">UCM_PD_POWER_DATA_OBJECT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCM_PD_POWER_DATA_OBJECT_INIT_VARIABLE_NON_BATTERY function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>