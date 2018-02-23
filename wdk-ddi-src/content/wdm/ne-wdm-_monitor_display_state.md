---
UID: NE:wdm._MONITOR_DISPLAY_STATE
title: "_MONITOR_DISPLAY_STATE"
author: windows-driver-content
description: Indicates the power state of the monitor being displayed on.
old-location: kernel\monitor_display_state.htm
old-project: kernel
ms.assetid: 50F5C1AD-BA51-4376-8093-E8596265FDAF
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PMONITOR_DISPLAY_STATE, PowerMonitorDim, MONITOR_DISPLAY_STATE, wdm/PowerMonitorOn, wdm/MONITOR_DISPLAY_STATE, wdm/PowerMonitorOff, PowerMonitorOn, kernel.monitor_display_state, _MONITOR_DISPLAY_STATE, wdm/PowerMonitorDim, MONITOR_DISPLAY_STATE enumeration [Kernel-Mode Driver Architecture], PowerMonitorOff"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	MONITOR_DISPLAY_STATE
product: Windows
targetos: Windows
req.typenames: "*PMONITOR_DISPLAY_STATE, MONITOR_DISPLAY_STATE"
req.product: Windows 10 or later.
---

# _MONITOR_DISPLAY_STATE Enumeration
Indicates the power state of the monitor being displayed on.

## Syntax
````
typedef enum _MONITOR_DISPLAY_STATE { 
  PowerMonitorOff  = 0,
  PowerMonitorOn,
  PowerMonitorDim
} MONITOR_DISPLAY_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>PowerMonitorDim</td>
                    <td>This indicates that the monitor is dim.</td>
                </tr>
            
                <tr>
                    <td>PowerMonitorOff</td>
                    <td>This indicates that the monitor is off.</td>
                </tr>
            
                <tr>
                    <td>PowerMonitorOn</td>
                    <td>This indicates that the monitor is on.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Ntpoapi.h) |