---
UID: NF:wdfdevice.WdfDeviceInitRegisterPowerStateChangeCallback
title: WdfDeviceInitRegisterPowerStateChangeCallback function
author: windows-driver-content
description: The WdfDeviceInitRegisterPowerStateChangeCallback method registers a driver-supplied event callback function that the framework calls when a device's power state machine changes state.
old-location: wdf\wdfdeviceinitregisterpowerstatechangecallback.htm
old-project: wdf
ms.assetid: f3c09dfb-d327-488b-8e5d-77a579d1e1f0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_c2199058-308e-4207-b035-30de28c64fa5.xml, WdfDeviceInitRegisterPowerStateChangeCallback, WdfDeviceInitRegisterPowerStateChangeCallback method, kmdf.wdfdeviceinitregisterpowerstatechangecallback, wdf.wdfdeviceinitregisterpowerstatechangecallback, wdfdevice/WdfDeviceInitRegisterPowerStateChangeCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
api_name:
-	WdfDeviceInitRegisterPowerStateChangeCallback
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceInitRegisterPowerStateChangeCallback function
<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfDeviceInitRegisterPowerStateChangeCallback</b> method registers a driver-supplied event callback function that the framework calls when a device's power state machine changes state.

## Syntax

````
NTSTATUS WdfDeviceInitRegisterPowerStateChangeCallback(
  _In_ PWDFDEVICE_INIT                                DeviceInit,
  _In_ WDF_DEVICE_POWER_STATE                         PowerState,
  _In_ PFN_WDF_DEVICE_POWER_STATE_CHANGE_NOTIFICATION EvtDevicePowerStateChange,
  _In_ ULONG                                          CallbackTypes
);
````

## Parameters

`DeviceInit`

A caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure.

`PowerState`

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_device_power_state.md">WDF_DEVICE_POWER_STATE</a> enumerator that identifies the power machine state for which the driver is requesting notification.

`EvtDevicePowerStateChange`

A caller-supplied pointer to the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_power_state_change_notification.md">EvtDevicePowerStateChange</a> event callback function.

`CallbackTypes`

An ORed combination of <a href="..\wdfdevice\ne-wdfdevice-_wdf_state_notification_type.md">WDF_STATE_NOTIFICATION_TYPE</a>-typed enumerators.


## Return Value

If the operation succeeds, <b>WdfDeviceInitRegisterPowerStateChangeCallback</b> returns STATUS_SUCCESS. Additional return values include:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There is insufficient memory to complete the operation.

</td>
</tr>
</table>

## Remarks

If your driver calls <b>WdfDeviceInitRegisterPowerStateChangeCallback</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.

For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="https://msdn.microsoft.com/5ef307c6-0310-4a83-a63f-3a6d96782013">State Machines in the Framework</a>.


#### Examples

The following code example registers an event callback function that the framework will call when the device's power state machine changes state.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>status = WdfDeviceInitRegisterPowerStateChangeCallback(
                                     DeviceInit,
                                     WdfDevStatePowerD0StartingConnectInterrupt,
                                     PciDrvPowerStateChangeCallback,
                                     StateNotificationAllStates
                                     );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (see Framework Library Versioning.) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, InitFreeDeviceCallback, InitFreeDeviceCreate, InitFreeNull, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI, PdoInitFreeDeviceCallback, PdoInitFreeDeviceCreate |