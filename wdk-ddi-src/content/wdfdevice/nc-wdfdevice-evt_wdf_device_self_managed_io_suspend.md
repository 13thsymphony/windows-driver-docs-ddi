---
UID: NC:wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoSuspend event callback function suspends a device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagediosuspend.htm
old-project: wdf
ms.assetid: 85a569ea-eb14-4453-9591-fc44afbd3a59
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_10625e27-0ff8-47fa-aff0-ddca49c7f326.xml, EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND, EvtDeviceSelfManagedIoSuspend, EvtDeviceSelfManagedIoSuspend callback function, kmdf.evtdeviceselfmanagediosuspend, wdf.evtdeviceselfmanagediosuspend, wdfdevice/EvtDeviceSelfManagedIoSuspend
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfdevice.h
api_name:
-	EvtDeviceSelfManagedIoSuspend
product: Windows
targetos: Windows
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---


# EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDeviceSelfManagedIoSuspend</i> event callback function suspends a device's self-managed I/O operations.

## Syntax

```
EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND EvtWdfDeviceSelfManagedIoSuspend;

NTSTATUS EvtWdfDeviceSelfManagedIoSuspend(
  WDFDEVICE Device
)
{...}
```

## Parameters

`Device`

A handle to a framework device object.


## Return Value

If the operation is successful, the <i>EvtDeviceSelfManagedIoSuspend</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework stops the device and removes its device objects.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md">EvtDeviceSelfManagedIoFlush</a> and <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a> callback functions. 



For more information about this callback function's return values, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/reporting-device-failures">Reporting Device Failures</a>.

## Remarks

To register an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, the framework calls it for one of the following reasons:

<ul>
<li>
The device is about to enter a low-power state.

</li>
<li>
The device is being removed or was surprise-removed.

</li>
<li>
The Plug and Play manager is about to redistribute the system's hardware resources among system's attached devices.

</li>
</ul>
Because you do not know which of these events causes the framework to call your driver, you must assume that the device might return to its working (D0) state.

If the device is about to enter a low-power state, the framework calls the driver's <i>EvtDeviceSelfManagedIoSuspend</i> callback function before it calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a> callback function.

If the callback function returns a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, and if the framework is attempting to lower the device's power, the framework stops the device and removes its device objects.

The <i>EvtDeviceSelfManagedIoSuspend</i> callback function must do whatever is needed to stop the device's self-managed I/O operations.

For more information about when the framework calls this callback function, see <a href="https://msdn.microsoft.com/9175ce95-196d-44bd-b31c-88386fa0d3d3">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="https://msdn.microsoft.com/539b3618-44bb-41fd-a9f2-ed6a377c94e2">Using Self-Managed I/O</a>.


#### Examples

To define an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDeviceSelfManagedIoSuspend</i> callback function that is named <i>MyDeviceSelfManagedIoSuspend</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND  MyDeviceSelfManagedIoSuspend;</pre>
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
 MyDeviceSelfManagedIoSuspend (
    WDFDEVICE  Device
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md">EvtDeviceSelfManagedIoFlush</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md">EvtDeviceSelfManagedIoCleanup</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>



<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>