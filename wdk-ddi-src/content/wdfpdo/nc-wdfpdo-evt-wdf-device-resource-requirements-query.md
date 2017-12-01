---
UID: NC.wdfpdo.EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
title: EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY
author: windows-driver-content
description: A bus driver's EvtDeviceResourceRequirementsQuery event callback function creates a resource requirements list that represents the device's required hardware resources.
old-location: wdf\evtdeviceresourcerequirementsquery.htm
old-project: wdf
ms.assetid: bacd7e7c-9f71-4dda-98ed-a8d813360943
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
req.alt-api: EvtDeviceResourceRequirementsQuery
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

# EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback



## -description
<p class="CCE_Message">[Applies to KMDF only]</p>
<p>A bus driver's <i>EvtDeviceResourceRequirementsQuery</i> event callback function creates a resource requirements list that represents the device's required hardware resources.</p>


## -prototype

````
EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY EvtDeviceResourceRequirementsQuery;

NTSTATUS EvtDeviceResourceRequirementsQuery(
  _In_ WDFDEVICE       Device,
  _In_ WDFIORESREQLIST IoResourceRequirementsList
)
{ ... }
````


## -parameters
<dl>

### -param <i>Device</i> [in]

<dd>
<p>A handle to a framework device object.</p>
</dd>

### -param <i>IoResourceRequirementsList</i> [in]

<dd>
<p>A handle to a framework resource-requirements-list object that represents an empty resource requirements list.</p>
</dd>
</dl>

## -returns
<p>If the driver did not encounter any errors, it must return STATUS_SUCCESS (whether or not it specifies any required hardware resource). If the driver encounters errors, it must return an NTSTATUS value that <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS</a> evaluates as <b>FALSE</b>.</p>

<p> 

For more information about this callback function's return values, see <a href="wdf.reporting_device_failures">Reporting Device Failures</a>.

</p>

## -remarks
<p>Framework-based bus drivers can provide an <i>EvtDeviceResourceRequirementsQuery</i> callback function. To register this callback function, bus drivers call <a href="..\wdfpdo\nf-wdfpdo-wdfpdoinitseteventcallbacks.md">WdfPdoInitSetEventCallbacks</a>.</p>

<p>The framework calls the bus driver's <i>EvtDeviceResourceRequirementsQuery</i> callback function to obtain a <a href="https://msdn.microsoft.com/c7a6997b-34f9-4dd9-b384-2321a8b5ce54">resource requirements list</a> for the device.</p>

<p>The driver must populate the supplied resource-requirements-list object with logical configurations of hardware resources that will allow the device to operate properly.</p>

<p>To create a resource requirements list, the driver calls <a href="wdf.wdf_resource_object_reference">framework resource-range-list object methods</a>, which add resource descriptors to logical configurations, and framework resource-requirements-list object methods, which add logical configurations to the resource requirements list.</p>

<p>For more information about hardware resources and creating resource requirements lists, see <a href="wdf.hardware_resources_for_kmdf_drivers">Hardware Resources for Framework-Based Drivers</a>.</p>

<p>If a driver is running on an operating system version that is earlier than Windows 7, a bus driver can use <i>EvtDeviceResourceRequirementsQuery</i> to <a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">set a device property</a> on a child device prior to enumerating the child.</p>

<p>To <a href="..\wdm\nf-wdm-iosetdevicepropertydata.md">set a device property</a> on Windows 7 or later, a bus driver can  <a href="wdf.preprocessing_and_postprocessing_irps">provide  a preprocess routine</a> for  <a href="https://msdn.microsoft.com/library/windows/hardware/hh285209">IRP_MN_DEVICE_ENUMERATED</a>.</p>

<p>To define an <i>EvtDeviceResourceRequirementsQuery</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>EvtDeviceResourceRequirementsQuery</i> callback function that is named <i>MyDeviceResourceRequirementsQuery</i>, use the <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> type as shown in this code example:</p>

<p>Then, implement your callback function as follows:</p>

<p>The <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> function type is defined in the Wdfpdo.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

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
<a href="wdf.evtdeviceresourcesquery">EvtDeviceResourcesQuery</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_DEVICE_RESOURCE_REQUIREMENTS_QUERY callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
