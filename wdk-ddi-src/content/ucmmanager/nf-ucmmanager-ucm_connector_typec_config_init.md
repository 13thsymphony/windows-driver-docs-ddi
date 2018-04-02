---
UID: NF:ucmmanager.UCM_CONNECTOR_TYPEC_CONFIG_INIT
title: UCM_CONNECTOR_TYPEC_CONFIG_INIT function
author: windows-driver-content
description: Initializes the UCM_CONNECTOR_TYPEC_CONFIG structure.
old-location: buses\ucm_connector_type_c_config_init.htm
old-project: usbref
ms.assetid: 10E155C2-907D-4D0E-87E9-A6B32E99D133
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCM_CONNECTOR_TYPEC_CONFIG_INIT, UCM_CONNECTOR_TYPE_C_CONFIG_INIT, UCM_CONNECTOR_TYPE_C_CONFIG_INIT function [Buses], buses.ucm_connector_type_c_config_init, ucmmanager/UCM_CONNECTOR_TYPE_C_CONFIG_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucmmanager.h
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
-	Ucmmanager.h
api_name:
-	UCM_CONNECTOR_TYPE_C_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# UCM_CONNECTOR_TYPEC_CONFIG_INIT function
Initializes the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187930">UCM_CONNECTOR_TYPEC_CONFIG</a> structure.

## Syntax

```
void UCM_CONNECTOR_TYPEC_CONFIG_INIT(
  PUCM_CONNECTOR_TYPEC_CONFIG Config,
  ULONG                       SupportedOperatingModes,
  ULONG                       SupportedPowerSourcingCapabilities
);
```

## Parameters

`Config`

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt187930">UCM_CONNECTOR_TYPEC_CONFIG</a> structure to initialize.

`SupportedOperatingModes`

Indicates the operating mode of the connector. This value is a bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187946">UCM_TYPEC_OPERATING_MODE</a>-typed flags.

`SupportedPowerSourcingCapabilities`

Indicates the power source capabilities of the connector. This value is a bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/mt187945">UCM_TYPEC_CURRENT</a>-typed flags.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |