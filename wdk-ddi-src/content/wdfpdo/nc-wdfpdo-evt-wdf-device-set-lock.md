---
UID: NC.wdfpdo.EVT_WDF_DEVICE_SET_LOCK
title: EVT_WDF_DEVICE_SET_LOCK
author: windows-driver-content
description: A driver's EvtDeviceSetLock event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.
old-location: wdf\evtdevicesetlock.htm
old-project: wdf
ms.assetid: 2ac42710-9f44-4982-a0d9-c49048870aeb
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDF_OBJECT_CONTEXT_TYPE_INFO, WDF_OBJECT_CONTEXT_TYPE_INFO, *PWDF_OBJECT_CONTEXT_TYPE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfpdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: EvtDeviceSetLock
req.alt-loc: Wdfpdo.h
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

# EVT_WDF_DEVICE_SET_LOCK callback



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>A driver's <i>EvtDeviceSetLock</i> event callback function locks the specified device so that it cannot be ejected, or unlocks the device so that it can be ejected.</p>


## -prototype

````
EVT_WDF_DEVICE_SET_LOCK EvtDeviceSetLock;

NTSTATUS EvtDeviceSetLock(
  _In_ WDFDEVICE Device,
  _In_ BOOLEAN   IsLocked
)
{ ... }
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param <i>IsLocked</i> [in]

<dd>
<p>A Boolean value that indicates whether the driver must lock or unlock the device. If <b>TRUE</b>, the driver must lock the device so that it cannot be ejected. If <b>FALSE</b>, the driver must unlock the device so that it can be ejected. </p>
</dd>
</dl>

## -returns
<p>If the driver successfully locks or unlocks the device, it must return STATUS_SUCCESS. Otherwise it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/7792201b-63bb-4db5-803d-2af02893d505">NT_SUCCESS</a> evaluates as <b>FALSE</b>.</p>

<p> 

For more information about this callback function's return values, see <a href="wdf.reporting_device_failures">Reporting Device Failures</a>.

</p>

## -remarks
<p>Framework-based bus drivers can provide an <i>EvtDeviceSetLock</i> callback function. To register this callback function, bus drivers call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.</p>

<p>The framework calls the driver's <i>EvtDeviceSetLock</i> callback function when the PnP manager requests the bus driver to lock or unlock one of its enumerated child devices. </p>

<p>Not implementing an <i>EvtDeviceSetLock</i> callback function for a device is equivalent to returning an NTSTATUS value that evaluates as <b>FALSE</b>.</p>

<p>For more information about return values, see <a href="wdf.supporting_ejectable_devices">Supporting Ejectable Devices</a>.</p>

<p>To define an <i>EvtDeviceSetLock</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtDeviceSetLock</i> callback function that is named <i>MyDeviceSetLock</i>, use the <b>EVT_WDF_DEVICE_SET_LOCK</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_DEVICE_SET_LOCK</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_SET_LOCK</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfpdo.h (include Wdf.h)</dt>
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
<a href="..\wdfpdo\nc-wdfpdo-evt-wdf-device-eject.md">EvtDeviceEject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_SET_LOCK callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
