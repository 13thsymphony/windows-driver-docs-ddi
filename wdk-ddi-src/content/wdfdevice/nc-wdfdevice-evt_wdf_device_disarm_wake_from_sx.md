---
UID: NC:wdfdevice.EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
title: EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX
author: windows-driver-content
description: A driver's EvtDeviceDisarmWakeFromSx event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.
old-location: wdf\evtdevicedisarmwakefromsx.htm
old-project: wdf
ms.assetid: 79bf7a42-5053-428a-a78b-dd8bdff93a69
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_ea30bcf7-25ce-493a-a8e0-310657a98c60.xml, EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX, EvtDeviceDisarmWakeFromSx, EvtDeviceDisarmWakeFromSx callback function, kmdf.evtdevicedisarmwakefromsx, wdf.evtdevicedisarmwakefromsx, wdfdevice/EvtDeviceDisarmWakeFromSx
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
-	EvtDeviceDisarmWakeFromSx
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceDisarmWakeFromSx</i> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while the device and system are in low-power states.

## Syntax

```
EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX EvtWdfDeviceDisarmWakeFromSx;

void EvtWdfDeviceDisarmWakeFromSx(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

None

## Remarks

To register an <i>EvtDeviceDisarmWakeFromSx</i> callback function, a driver must call  <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>.

If the driver has registered this callback function, the framework calls it after the framework has determined that system power is being restored, and after the bus driver completes the <a href="https://msdn.microsoft.com/ed582644-af51-4841-be59-6a3deb6d9de5">wait/wake IRP</a>. Before calling the driver's <i>EvtDeviceDisarmWakeFromSx</i> callback function, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_enable.md">EvtInterruptEnable</a>, and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md">EvtDeviceWakeFromSxTriggered</a> callback functions.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function must perform any hardware operations that are needed to disable the device's ability to trigger a wake signal after the power has been lowered.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about this callback function, see <a href="https://msdn.microsoft.com/519dcd1a-9975-48b1-a032-04348b903ac5">Supporting System Wake-Up</a>.

The <i>EvtDeviceDisarmWakeFromSx</i> callback function is called at IRQL = PASSIVE_LEVEL. You should not make this callback function <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-pageable-code-in-a-kmdf-driver">pageable</a>.


#### Examples

To define an <i>EvtDeviceDisarmWakeFromSx</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceDisarmWakeFromSx</i> callback function that is named <i>MyDeviceDisarmWakeFromSx</i>, use the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX  MyDeviceDisarmWakeFromSx;</pre>
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
VOID
 MyDeviceDisarmWakeFromSx (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL (see Remarks section) |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md">EvtDeviceArmWakeFromSx</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md">EvtDeviceWakeFromSxTriggered</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md">EvtDeviceDisarmWakeFromS0</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_DISARM_WAKE_FROM_SX callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>