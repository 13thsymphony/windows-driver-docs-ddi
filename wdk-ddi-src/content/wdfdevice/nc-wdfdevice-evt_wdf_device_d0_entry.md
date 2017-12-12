---
UID: NC.wdfdevice.EVT_WDF_DEVICE_D0_ENTRY
title: EVT_WDF_DEVICE_D0_ENTRY
author: windows-driver-content
description: A driver's EvtDeviceD0Entry event callback function performs operations that are needed when the driver's device enters the D0 power state.
old-location: wdf\evtdeviced0entry.htm
old-project: wdf
ms.assetid: 0cfabb0f-2d5e-4445-8683-d2916de5b549
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WDF_REL_TIMEOUT_IN_US
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtDeviceD0Entry
req.alt-loc: Wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_D0_ENTRY callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceD0Entry</i> event callback function performs operations that are needed when the driver's device enters the D0 power state.



## -prototype

````
EVT_WDF_DEVICE_D0_ENTRY EvtDeviceD0Entry;

NTSTATUS EvtDeviceD0Entry(
  _In_ WDFDEVICE              Device,
  _In_ WDF_POWER_DEVICE_STATE PreviousState
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param PreviousState [in]

A <a href="wdf.wdf_power_device_state">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the previous device power state.


## -returns
If the <i>EvtDeviceD0Entry</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="wdf.reporting_device_failures">Reporting Device Failures</a>.



The framework does not call the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function after the <i>EvtDeviceD0Entry</i> callback function returns a status value for which NT_SUCCESS(status) equals <b>FALSE</b>. 



## -remarks
To register an <i>EvtDeviceD0Entry</i> callback function for a device, a driver must call <a href="wdf.wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceD0Entry</i> callback function for a device, the framework calls the function each time the device enters its working (D0) state. A device will enter the D0 state when one of the following occurs:

A device is enumerated (because the device was plugged in or the system was rebooted).

The system and all of its devices return to their working states from a low-power state.

The device returns to its working state after it entered a low-power state because it was idle (if the device supports low-power idle).

The Plug and Play manager has redistributed the system's hardware resources among the system's devices.

The framework calls the <i>EvtDeviceD0Entry</i> callback function immediately after the device enters its working (D0) state and is available to the driver, but before the device's interrupts have been enabled. The <i>PreviousState</i> parameter identifies the device power state that the device was in before it entered the D0 state.   When the framework first calls <i>EvtDeviceD0Entry</i>, it provides a <i>PreviousState</i> value of <b>WdfPowerDeviceD3Final</b>.

The callback function must perform any operations that are needed to make the device fully operational, such as loading firmware or enabling device capabilities that are disabled when the device is in a low-power state. 

If the <i>EvtDeviceD0Entry</i> callback function returns a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework does the following:

If the device is starting for the first time, the framework begins an <a href="wdf.a_user_unplugs_a_device#orderly_removal#orderly_removal">orderly removal</a> sequence for the device.

If the device is returning from a low-power state to its working state, the framework begins a <a href="wdf.a_user_unplugs_a_device#surprise_removal#surprise_removal">surprise removal</a> sequence for the device.

The framework does not call the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function in either of these situations.

For more information about when the framework calls the <i>EvtDeviceD0Entry</i> callback function, see <a href="wdf.pnp_and_power_management_scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="wdf.supporting_pnp_and_power_management_in_function_drivers">Supporting PnP and Power Management in Function Drivers</a>.

The <i>EvtDeviceD0Entry</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="wdf.creating_pageable_code_in_a_kmdf_driver">pageable</a>.

To define an <i>EvtDeviceD0Entry</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceD0Entry</i> callback function that is named <i>MyDeviceD0Entry</i>, use the <b>EVT_WDF_DEVICE_D0_ENTRY</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_D0_ENTRY</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_D0_ENTRY</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.0

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
2.0

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_D0_ENTRY callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

