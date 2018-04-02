---
UID: NF:ucmmanager.UCM_MANAGER_CONFIG_INIT
title: UCM_MANAGER_CONFIG_INIT function
author: windows-driver-content
description: Initializes a UCM_MANAGER_CONFIG structure.
old-location: buses\ucm_manager_config_init.htm
old-project: usbref
ms.assetid: 5247D5F0-8422-48C1-81AF-98C8A3537FAD
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UCM_MANAGER_CONFIG_INIT, UCM_MANAGER_CONFIG_INIT function [Buses], buses.ucm_manager_config_init, ucmmanager/UCM_MANAGER_CONFIG_INIT
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
-	UCM_MANAGER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: PORT_DATA_1, *PPORT_DATA_1
req.product: Windows 10 or later.
---


# UCM_MANAGER_CONFIG_INIT function
Initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a> structure.

## Syntax

```
void UCM_MANAGER_CONFIG_INIT(
  PUCM_MANAGER_CONFIG Config
);
```

## Parameters

`Config`

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a> structure to initialize.


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

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187932">UCM_MANAGER_CONFIG</a>