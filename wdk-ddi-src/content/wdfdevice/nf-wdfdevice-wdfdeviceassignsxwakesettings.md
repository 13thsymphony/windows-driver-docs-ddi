---
UID: NF:wdfdevice.WdfDeviceAssignSxWakeSettings
title: WdfDeviceAssignSxWakeSettings function
author: windows-driver-content
description: The WdfDeviceAssignSxWakeSettings method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.
old-location: wdf\wdfdeviceassignsxwakesettings.htm
old-project: wdf
ms.assetid: af25d03f-32c5-4e2c-930f-1b905edc566b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_1a9b9467-862d-422a-9cf6-501d1ddefe5e.xml, WdfDeviceAssignSxWakeSettings, WdfDeviceAssignSxWakeSettings method, kmdf.wdfdeviceassignsxwakesettings, wdf.wdfdeviceassignsxwakesettings, wdfdevice/WdfDeviceAssignSxWakeSettings
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
req.ddi-compliance: DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfDeviceAssignSxWakeSettings
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceAssignSxWakeSettings function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAssignSxWakeSettings</b> method provides driver-supplied information about a device's ability to trigger a wake signal while both the device and the system are in a low-power state.

## Syntax

```
NTSTATUS WdfDeviceAssignSxWakeSettings(
  WDFDEVICE                              Device,
  PWDF_DEVICE_POWER_POLICY_WAKE_SETTINGS Settings
);
```

## Parameters

`Device`

A handle to a framework device object.

`Settings`

A pointer to a caller-supplied <a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure.


## Return Value

If the operation succeeds, <b>WdfDeviceAssignSxWakeSettings</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The calling driver is not the device's power policy owner.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid <i>Settings</i> value is detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure is incorrect. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>
</td>
<td width="60%">
The bus driver indicates the device cannot trigger a wake signal, or the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure contains an invalid device power state.


</td>
</tr>
</table>
 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

For more information, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.


#### Examples

The following code example initializes a WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS structure and then calls <b>WdfDeviceAssignSxWakeSettings</b>. The example uses the default settings that <a href="https://msdn.microsoft.com/library/windows/hardware/ff551279">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT</a> sets.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS  wakeSettings;
NTSTATUS  status = STATUS_SUCCESS;

WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT(&amp;wakeSettings);

status = WdfDeviceAssignSxWakeSettings(
                                       device,
                                       &amp;wakeSettings
                                       );
if (!NT_SUCCESS(status)) {
    return status;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551277">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545903">WdfDeviceAssignS0IdleSettings</a>