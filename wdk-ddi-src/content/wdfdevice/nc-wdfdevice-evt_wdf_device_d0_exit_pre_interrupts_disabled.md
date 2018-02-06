---
UID: NC:wdfdevice.EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
title: EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED
author: windows-driver-content
description: A driver's EvtDeviceD0ExitPreInterruptsDisabled event callback function performs device-specific operations that are required before the driver disables the device's hardware interrupts.
old-location: wdf\evtdeviced0exitpreinterruptsdisabled.htm
old-project: wdf
ms.assetid: 8f57c3b3-2dcf-44a3-a3c2-c9585bdfa253
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtdeviced0exitpreinterruptsdisabled, EvtDeviceD0ExitPreInterruptsDisabled callback function, EvtDeviceD0ExitPreInterruptsDisabled, EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED, EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED, wdfdevice/EvtDeviceD0ExitPreInterruptsDisabled, DFDeviceObjectGeneralRef_f10df6b2-b5ef-49ad-8333-9289c164ea40.xml, kmdf.evtdeviced0exitpreinterruptsdisabled
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfdevice.h
apiname:
-	EvtDeviceD0ExitPreInterruptsDisabled
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED function
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

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_device_state.md">WDF_POWER_DEVICE_STATE</a>-typed enumerator that identifies the device power state that the device is about to enter.


## Return Value

If the <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 

For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## Remarks

To register an <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

The <i>EvtDeviceD0ExitPreInterruptsDisabled</i> callback function is called at IRQL = PASSIVE_LEVEL, before the framework calls the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_disable.md">EvtInterruptDisable</a> callback function. A driver can provide this function if it must perform device-specific operations before disables an interrupt, if those operations should not be performed at IRQL = DIRQL in the <i>EvtInterruptDisable</i> callback function.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about handling interrupts, see <a href="https://msdn.microsoft.com/08460510-6e5f-4c02-8086-9caa9b4b4c2d">Handling Hardware Interrupts</a>.

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

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_D0_EXIT_PRE_INTERRUPTS_DISABLED callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>