---
UID: NC.wdfdevice.EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND
title: EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND
author: windows-driver-content
description: A driver's EvtDeviceSelfManagedIoSuspend event callback function suspends a device's self-managed I/O operations.
old-location: wdf\evtdeviceselfmanagediosuspend.htm
old-project: wdf
ms.assetid: 85a569ea-eb14-4453-9591-fc44afbd3a59
ms.author: windowsdriverdev
ms.date: 11/30/2017
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
req.alt-api: EvtDeviceSelfManagedIoSuspend
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>A driver's <i>EvtDeviceSelfManagedIoSuspend</i> event callback function suspends a device's self-managed I/O operations.</p>


## -prototype

````
EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND EvtDeviceSelfManagedIoSuspend;

NTSTATUS EvtDeviceSelfManagedIoSuspend(
  _In_ WDFDEVICE Device
)
{ ... }
````


## -parameters
<dl>

### -param Device [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>
</dl>

## -returns
<p>If the operation is successful, the <i>EvtDeviceSelfManagedIoSuspend</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. If NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, the framework stops the device and removes its device objects.</p>

<p>If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-flush.md">EvtDeviceSelfManagedIoFlush</a> and <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-cleanup.md">EvtDeviceSelfManagedIoCleanup</a> callback functions. 

</p>

<p>For more information about this callback function's return values, see <a href="wdf.reporting_device_failures">Reporting Device Failures</a>.</p>

## -remarks
<p>To register an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, a driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md">WdfDeviceInitSetPnpPowerEventCallbacks</a>. </p>

<p>If the driver has registered an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, the framework calls it for one of the following reasons:</p>

<p>The device is about to enter a low-power state.</p>

<p>The device is being removed or was surprise-removed.</p>

<p>The Plug and Play manager is about to redistribute the system's hardware resources among system's attached devices.</p>

<p>Because you do not know which of these events causes the framework to call your driver, you must assume that the device might return to its working (D0) state.</p>

<p>If the device is about to enter a low-power state, the framework calls the driver's <i>EvtDeviceSelfManagedIoSuspend</i> callback function before it calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-d0-exit.md">EvtDeviceD0Exit</a> callback function.</p>

<p>If the callback function returns a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>, and if the framework is attempting to lower the device's power, the framework stops the device and removes its device objects.</p>

<p>The <i>EvtDeviceSelfManagedIoSuspend</i> callback function must do whatever is needed to stop the device's self-managed I/O operations.</p>

<p>For more information about when the framework calls this callback function, see <a href="wdf.pnp_and_power_management_scenarios">PnP and Power Management Scenarios</a>.</p>

<p>For more information about drivers that provide this callback function, see <a href="wdf.using_self_managed_i_o">Using Self-Managed I/O</a>.</p>

<p>To define an <i>EvtDeviceSelfManagedIoSuspend</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtDeviceSelfManagedIoSuspend</i> callback function that is named <i>MyDeviceSelfManagedIoSuspend</i>, use the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-cleanup.md">EvtDeviceSelfManagedIoCleanup</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-flush.md">EvtDeviceSelfManagedIoFlush</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-init.md">EvtDeviceSelfManagedIoInit</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-self-managed-io-restart.md">EvtDeviceSelfManagedIoRestart</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SELF_MANAGED_IO_SUSPEND callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
