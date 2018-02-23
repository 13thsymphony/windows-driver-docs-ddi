---
UID: NE:wditypes._WDI_IHV_TASK_PRIORITY
title: "_WDI_IHV_TASK_PRIORITY"
author: windows-driver-content
description: The WDI_IHV_TASK_PRIORITY enumeration defines IHV task priorities.
old-location: netvista\wdi_ihv_task_priority.htm
old-project: netvista
ms.assetid: 606CF45C-5398-4157-92A7-382B6162D806
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WDI_IHV_TASK_PRIORITY enumeration [Network Drivers Starting with Windows Vista], wditypes/WDI_IHV_TASK_PRIORITY, wditypes/WDI_IHV_TASK_PRIORITY_HIGH, WDI_IHV_TASK_PRIORITY, netvista.wdi_ihv_task_priority, WDI_IHV_TASK_PRIORITY_MEDIUM, wditypes/WDI_IHV_TASK_PRIORITY_LOW, wditypes/WDI_IHV_TASK_PRIORITY_MEDIUM, WDI_IHV_TASK_PRIORITY_LOW, netvista.wifi_ihv_task_priority, _WDI_IHV_TASK_PRIORITY, WDI_IHV_TASK_PRIORITY_HIGH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	wditypes.hpp
apiname:
-	WDI_IHV_TASK_PRIORITY
product: Windows
targetos: Windows
req.typenames: WDI_IHV_TASK_PRIORITY
req.product: Windows 10 or later.
---

# _WDI_IHV_TASK_PRIORITY Enumeration
The WDI_IHV_TASK_PRIORITY enumeration defines IHV task priorities.

## Syntax
````
typedef enum _WDI_IHV_TASK_PRIORITY { 
  WDI_IHV_TASK_PRIORITY_HIGH    = 1,
  WDI_IHV_TASK_PRIORITY_MEDIUM  = 2,
  WDI_IHV_TASK_PRIORITY_LOW     = 3
} WDI_IHV_TASK_PRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>WDI_IHV_TASK_PRIORITY_HIGH</td>
                    <td>High priority.</td>
                </tr>
            
                <tr>
                    <td>WDI_IHV_TASK_PRIORITY_LOW</td>
                    <td>Low priority.</td>
                </tr>
            
                <tr>
                    <td>WDI_IHV_TASK_PRIORITY_MEDIUM</td>
                    <td>Medium priority.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |