---
UID: NE:wdm._MONITOR_DISPLAY_STATE
title: "_MONITOR_DISPLAY_STATE"
author: windows-driver-content
description: Indicates the power state of the monitor being displayed on.
old-location: kernel\monitor_display_state.htm
old-project: kernel
ms.assetid: 50F5C1AD-BA51-4376-8093-E8596265FDAF
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PMONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE enumeration [Kernel-Mode Driver Architecture], PowerMonitorDim, PowerMonitorOff, PowerMonitorOn, _MONITOR_DISPLAY_STATE, kernel.monitor_display_state, wdm/MONITOR_DISPLAY_STATE, wdm/PowerMonitorDim, wdm/PowerMonitorOff, wdm/PowerMonitorOn"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Ntpoapi.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	MONITOR_DISPLAY_STATE
product:
- Windows
targetos: Windows
req.typenames: MONITOR_DISPLAY_STATE, *PMONITOR_DISPLAY_STATE
req.product: Windows 10 or later.
---

# _MONITOR_DISPLAY_STATE Enumeration
Indicates the power state of the monitor being displayed on.

## Syntax
```
typedef enum _MONITOR_DISPLAY_STATE {
  PowerMonitorOff  ,
  PowerMonitorOn   ,
  PowerMonitorDim
} *PMONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE;
```

## Constants

<table>
            
                <tr>
                    <td>PowerMonitorOff</td>
                    <td>This indicates that the monitor is off.</td>
                </tr>
            
                <tr>
                    <td>PowerMonitorOn</td>
                    <td>This indicates that the monitor is on.</td>
                </tr>
            
                <tr>
                    <td>PowerMonitorDim</td>
                    <td>This indicates that the monitor is dim.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Ntpoapi.h) |