---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
title: EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
author: windows-driver-content
description: A driver's EvtDeviceD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\evtdeviced0exitpreinterruptsdisabled.htm
old-project: wdf
ms.assetid: 8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_f10df6b2-b5ef-49ad-8333-9289c164ea40.xml, EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED, EvtDeviceD0ExitPreInterruptsDisabled, EvtDeviceD0ExitPreInterruptsDisabled callback function, kmdf.evtdeviced0exitpreinterruptsdisabled, wdf.evtdeviced0exitpreinterruptsdisabled, wdfdevice/EvtDeviceD0ExitPreInterruptsDisabled
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceD0ExitPreInterruptsDisabled
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceD0ExitPreInterruptsDisabled</i> event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.

## Syntax

```
EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED EvtWdfDeviceD0ExitPreInterruptsDisabled;

NTSTATUS EvtWdfDeviceD0ExitPreInterruptsDisabled(
  WDFDEVICE Device,
  WDF_POWER_DEVICE_STATE TargetState
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.

`TargetState`

A <a href="..\wdfdevice\ne-wdfdevice-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the device power state that the device is about to enter.


## Return Value

If the <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## Remarks

To register an <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function is called at IRQL = PASSIVE_LEVEL, before the framework calls the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function. A driver can provide this function if it must perform device-specific operations before disables an interrupt, if those operations should not be performed at IRQL = DIRQL in the <i>EvtInterruptDisable</i> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about handling interrupts, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.


#### Examples

To define an <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function that is named <i>MyDeviceD0ExitPreInterruptsDisabled</i>, use the <b>EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED  MyDeviceD0ExitPreInterruptsDisabled;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
NTSTATUS
 MyDeviceD0ExitPreInterruptsDisabled (
    WDFDEVICE  Device,
    WDF_POWER_DEVICE_STATE  TargetState
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled.md">EvtDeviceD0EntryPostInterruptsEnabled</a>