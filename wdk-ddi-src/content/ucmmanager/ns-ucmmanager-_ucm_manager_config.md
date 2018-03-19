---
UID: NS:ucmmanager._UCM_MANAGER_CONFIG
title: "_UCM_MANAGER_CONFIG"
author: windows-driver-content
description: Describes the configuration options for the UCM Manager. An initialized UCM_MANAGER_CONFIG structure is an input parameter value to UcmInitializeDevice.
old-location: buses\ucm_manager_config.htm
old-project: usbref
ms.assetid: 2B9539D7-6125-4912-9572-13FA7CA671D9
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCM_MANAGER_CONFIG, PUCM_MANAGER_CONFIG, PUCM_MANAGER_CONFIG structure pointer [Buses], UCM_MANAGER_CONFIG, UCM_MANAGER_CONFIG structure [Buses], _UCM_MANAGER_CONFIG, buses.ucm_manager_config, ucmmanager/PUCM_MANAGER_CONFIG, ucmmanager/UCM_MANAGER_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	UCM_MANAGER_CONFIG
product: Windows
targetos: Windows
req.typenames: UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG
req.product: Windows 10 or later.
---

# _UCM_MANAGER_CONFIG structure
Describes the configuration options for the UCM Manager. An initialized <b>UCM_MANAGER_CONFIG</b> structure is an input parameter value to   <a href="..\ucmmanager\nf-ucmmanager-ucminitializedevice.md">UcmInitializeDevice</a>.

## Syntax
````
typedef struct _UCM_MANAGER_CONFIG {
  ULONG                Size;
} UCM_MANAGER_CONFIG, *PUCM_MANAGER_CONFIG;
````

## Members


`Size`

Size of the <b>UCM_MANAGER_CONFIG</b> structure. Initialize this structure by calling <a href="..\ucmmanager\nf-ucmmanager-ucm_manager_config_init.md">UCM_MANAGER_CONFIG_INIT</a>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** | 2.15 |
| **Header** | ucmmanager.h (include Ucmcx.h) |

## See Also

<a href="..\ucmmanager\nf-ucmmanager-ucm_manager_config_init.md">UCM_MANAGER_CONFIG_INIT</a>