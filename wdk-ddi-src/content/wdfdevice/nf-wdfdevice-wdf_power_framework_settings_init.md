---
UID: NF:wdfdevice.WDF_POWER_FRAMEWORK_SETTINGS_INIT
title: WDF_POWER_FRAMEWORK_SETTINGS_INIT function
author: windows-driver-content
description: The WDF_POWER_FRAMEWORK_SETTINGS_INIT function initializes a WDF_POWER_FRAMEWORK_SETTINGS structure.
old-location: wdf\wdf_power_framework_settings_init.htm
old-project: wdf
ms.assetid: 26F872A2-7727-4346-BA80-779D082EAE9D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_POWER_FRAMEWORK_SETTINGS_INIT, WDF_POWER_FRAMEWORK_SETTINGS_INIT function, kmdf.wdf_power_framework_settings_init, wdf.wdf_power_framework_settings_init, wdfdevice/WDF_POWER_FRAMEWORK_SETTINGS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfdevice.h
api_name:
-	WDF_POWER_FRAMEWORK_SETTINGS_INIT
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WDF_POWER_FRAMEWORK_SETTINGS_INIT function
<p class="CCE_Message">[Applies to KMDF only]


    The 
  <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.

## Syntax

```
void WDF_POWER_FRAMEWORK_SETTINGS_INIT(
  PWDF_POWER_FRAMEWORK_SETTINGS PowerFrameworkSettings
);
```

## Parameters

`PowerFrameworkSettings`

A pointer to a driver-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a> structure.


## Return Value

This function does not return a value.

## Remarks

The <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b> function zeros the specified <a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a> structure and sets the structure's <b>Size</b> member.


#### Examples

For a code example that uses <b>WDF_POWER_FRAMEWORK_SETTINGS_INIT</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>.

<div class="code"></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406489">WDF_POWER_FRAMEWORK_SETTINGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451097">WdfDeviceWdmAssignPowerFrameworkSettings</a>