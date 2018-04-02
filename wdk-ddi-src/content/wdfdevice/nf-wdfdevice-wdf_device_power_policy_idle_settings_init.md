---
UID: NF:wdfdevice.WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
title: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function
author: windows-driver-content
description: The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure.
old-location: wdf\wdf_device_power_policy_idle_settings_init.htm
old-project: wdf
ms.assetid: e5a80021-1d9d-42f4-9344-9dd8d9524d0b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_1aaae0d7-3b13-43f6-b7e4-7c105b2e41b2.xml, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT, WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function, kmdf.wdf_device_power_policy_idle_settings_init, wdf.wdf_device_power_policy_idle_settings_init, wdfdevice/WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	wdfdevice.h
api_name:
-	WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
product:
- Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function initializes a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

## Syntax

```
void WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(
  PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS Settings,
  WDF_POWER_POLICY_S0_IDLE_CAPABILITIES  IdleCaps
);
```

## Parameters

`Settings`

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

`IdleCaps`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff552429">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator.


## Return Value

None

## Remarks

First, the <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. 

Then, the function sets the structure's <b>IdleTimeout</b> member to <b>IdleTimeoutDefaultValue</b>, sets the <b>UserControlOfIdleSettings</b> member to <b>IdleAllowUserControl</b>, and sets the <b>Enabled</b> member to <b>WdfUseDefault</b>. 

In addition, the function sets the <b>PowerUpIdleDeviceOnSystemWake</b> member to  <b>WdfUseDefault</b> and the <b>IdleTimeoutType</b> member to <b>DriverManagedIdleTimeout</b>.

 In addition, the function sets the <b>ExcludeD3Cold</b> member to <b>WdfUseDefault</b>.

Next, the function sets the structure's <b>IdleCaps</b> member to the value that the <i>IdleCaps</i> parameter specifies. 

Finally, if the <i>IdleCaps</i> parameter specifies <b>IdleUsbSelectiveSuspend</b> or <b>IdleCanWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>. If the <i>IdleCaps</i> parameter specifies <b>IdleCannotWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceD3</b>.


#### Examples

For a code example that uses <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff545903">WdfDeviceAssignS0IdleSettings</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551270">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>