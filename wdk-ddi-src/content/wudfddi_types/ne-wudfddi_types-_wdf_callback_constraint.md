---
UID: NE:wudfddi_types._WDF_CALLBACK_CONSTRAINT
title: "_WDF_CALLBACK_CONSTRAINT"
author: windows-driver-content
description: WDF_CALLBACK_CONSTRAINT enumeration
old-location: wdf\wdf_callback_constraint.htm
old-project: wdf
ms.assetid: 118a9dcc-8dd4-454a-bab2-1558821781a7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: "_WDF_CALLBACK_CONSTRAINT, wudfddi_types/WdfDeviceLevel, WDF_CALLBACK_CONSTRAINT, None, WdfLevelReserved, wudfddi_types/WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS enumeration, wdf.wdf_callback_constraint, WdfDeviceLevel, wudfddi_types/None, WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS, wudfddi_types/WdfLevelReserved"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
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
-	wudfddi_types.h
apiname:
-	WDF_CALLBACK_CONSTRAINT
product: Windows
targetos: Windows
req.typenames: WDF_CALLBACK_CONSTRAINT
req.product: Windows 10 or later.
---

# _WDF_CALLBACK_CONSTRAINT Enumeration


## Syntax
````
typedef enum _WDF_CALLBACK_CONSTRAINT { 
  None              = 0,
  WdfDeviceLevel    = 1,
  WdfLevelReserved  = 2
} WDF_CALLBACK_CONSTRAINT;
````

## Constants

<table>
            
                <tr>
                    <td>None</td>
                    <td>No callback functions into the driver are synchronized.  The driver must handle all synchronization.</td>
                </tr>
            
                <tr>
                    <td>WdfDeviceLevel</td>
                    <td>All callback functions into the driver that are associated with the device are synchronized, including all callback functions that are associated with I/O queues. Only one event handler that is associated with the device can run at any given time.</td>
                </tr>
            
                <tr>
                    <td>WdfLevelMaximum</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>WdfLevelReserved</td>
                    <td>Reserved.</td>
                </tr>
</table>

    ## Remarks

        Note that the above locking models apply only for I/O (that is, open, read, write, and device I/O control) operations and not for Plug and Play (PnP) and power management notifications.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi_types.h (include Wdf.h) |