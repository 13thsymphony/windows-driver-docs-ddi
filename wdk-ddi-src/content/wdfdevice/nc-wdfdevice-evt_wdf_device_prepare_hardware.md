---
UID: NC.wdfdevice.EVT_WDF_DEVICE_PREPARE_HARDWARE
title: EVT_WDF_DEVICE_PREPARE_HARDWARE
author: windows-driver-content
description: A driver's EvtDevicePrepareHardware event callback function performs any operations that are needed to make a device accessible to the driver.
old-location: wdf\evtdevicepreparehardware.htm
old-project: wdf
ms.assetid: a3d4a983-8a75-44be-bd72-8673d89f9f87
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
req.alt-api: EvtDevicePrepareHardware
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
req.product: Windows 10 or later.
---

# EVT_WDF_DEVICE_PREPARE_HARDWARE callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtDevicePrepareHardware</i> event callback function performs any operations that are needed to make a device accessible to the driver.



## -prototype

````
EVT_WDF_DEVICE_PREPARE_HARDWARE EvtDevicePrepareHardware;

NTSTATUS EvtDevicePrepareHardware(
  _In_ WDFDEVICE    Device,
  _In_ WDFCMRESLIST ResourcesRaw,
  _In_ WDFCMRESLIST ResourcesTranslated
)
{ ... }
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param ResourcesRaw [in]

A handle to a framework resource-list object that identifies the raw hardware resources that the Plug and Play manager has assigned to the device.


### -param ResourcesTranslated [in]

A handle to a framework resource-list object that identifies the translated hardware resources that the Plug and Play manager has assigned to the device.


## -returns
If the <i>EvtDevicePrepareHardware</i> callback function encounters no errors, it must return STATUS_SUCCESS or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>. Otherwise, it must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. Do not return STATUS_NOT_SUPPORTED.

If NT_SUCCESS(status) equals <b>FALSE</b>, the framework calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function. 

For more information about this callback function's return values, see <a href="wdf.reporting_device_failures">Reporting Device Failures</a>.


## -remarks
To register an <i>EvtDevicePrepareHardware</i> callback function, a driver must call <a href="wdf.wdfdeviceinitsetpnppowereventcallbacks">WdfDeviceInitSetPnpPowerEventCallbacks</a>. 

If the driver has registered an <i>EvtDevicePrepareHardware</i> callback function for a device, the framework calls the function after the Plug and Play manager has assigned hardware resources to the device and after the device has entered its uninitialized D0 state. (The Plug and Play manager always starts a parent device before it starts that device's child devices.)

The framework calls the driver's <i>EvtDevicePrepareHardware</i> callback function before calling the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function.

The <i>EvtDevicePrepareHardware</i> callback function accesses the device's raw and translated hardware resources by using the <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that it receives. The callback function can call <a href="wdf.wdfcmresourcelistgetcount">WdfCmResourceListGetCount</a> and <a href="wdf.wdfcmresourcelistgetdescriptor">WdfCmResourceListGetDescriptor</a> to traverse the resource lists. This callback function cannot modify the resource lists.

For more information about resource lists and the order in which the resources appear, see <a href="wdf.raw_and_translated_resources">raw and translated hardware resources</a>.

Typically, your driver's <i>EvtDevicePrepareHardware</i> callback function does the following, if necessary:

Maps physical memory addresses to virtual addresses so the driver can access memory that is assigned to the device

Determines the device's revision number

Configures USB devices

Obtains <a href="wdf.using_driver_defined_interfaces">driver-defined interfaces</a> from other drivers

Optionally, your driver's <i>EvtDevicePrepareHardware</i> callback function might queue a work item to complete any other time-intensive configuration tasks. Using a work item for such operations can help ensure that your device's start up time does not increase the system boot time. For more information, see <a href="wdf.using_framework_work_items">Using Framework Work Items</a>.

Typically, all other hardware initialization operations, including loading firmware, should take place each time that the device enters its working (D0) state and should therefore take place in the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> callback function.

The <i>ResourcesRaw</i> and <i>ResourcesTranslated</i> handles that the <i>EvtDevicePrepareHardware</i> callback function receives remain valid until the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> callback function returns.

For more information about hardware resources, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.

For more information about when the framework calls this callback function, see <a href="wdf.pnp_and_power_management_scenarios">PnP and Power Management Scenarios</a>.

For more information about drivers that provide this callback function, see <a href="wdf.supporting_pnp_and_power_management_in_function_drivers">Supporting PnP and Power Management in Function Drivers</a>.

To define an <i>EvtDevicePrepareHardware</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtDevicePrepareHardware</i> callback function that is named <i>MyDevicePrepareHardware</i>, use the <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> function type is defined in the Wdfdevice.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_PREPARE_HARDWARE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_PREPARE_HARDWARE callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

