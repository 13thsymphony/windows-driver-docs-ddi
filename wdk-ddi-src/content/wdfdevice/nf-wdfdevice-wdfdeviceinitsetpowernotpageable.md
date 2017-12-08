---
UID: NF.wdfdevice.WdfDeviceInitSetPowerNotPageable
title: WdfDeviceInitSetPowerNotPageable function
author: windows-driver-content
description: The WdfDeviceInitSetPowerNotPageable method informs the power manager that the driver will not access pageable data while the system is transitioning between a sleeping state and the working (S0) state.
old-location: wdf\wdfdeviceinitsetpowernotpageable.htm
old-project: wdf
ms.assetid: c0f39e50-8bf1-4ac9-8610-18915b375797
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfDeviceInitSetPowerNotPageable
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
req.alt-api: WdfDeviceInitSetPowerNotPageable
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPowerNotPageable function



## -description
<p class="CCE_Message">[Applies to KMDF only]
The <b>WdfDeviceInitSetPowerNotPageable</b> method informs the power manager that the driver will not access <a href="wdf.creating_pageable_code_in_a_kmdf_driver">pageable</a> data while the system is transitioning between a sleeping state and the working (S0) state. 


## -syntax

````
VOID WdfDeviceInitSetPowerNotPageable(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters

### -param DeviceInit [in]

A caller-supplied pointer to a <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure.

## -returns
None

## -remarks
If your function driver or bus driver calls <b>WdfDeviceInitSetPowerNotPageable</b>, the system paging file's device might not be in its working (D0) state when your driver's device <a href="wdf.a_device_enters_a_low_power_state">enters a low-power state</a> or <a href="wdf.a_device_returns_to_its_working_state">returns to its working state</a>. Therefore, during your device's power transitions, your driver must not perform any operations that might cause the operating system to access the paging file. Such operations include accessing files, the registry, or paged pool. 

By default, the framework enables access to pageable data for function drivers. The framework uses the parent device's setting for each child device that a bus driver enumerates, unless the bus driver calls either <a href="wdf.wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b> for the child device. If you write a bus driver that calls <b>WdfDeviceInitSetPowerPageable</b> for a child device, no drivers in the child device's stack can call <b>WdfDeviceInitSetPowerNotPageable</b>. 

Calling <a href="wdf.wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b> from a filter driver has no effect. The framework uses the setting that the next-lower driver specifies.

Most drivers do not need to call <a href="wdf.wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a> or <b>WdfDeviceInitSetPowerNotPageable</b>. Instead, you should let the framework use the default setting that is appropriate for your driver. However, your driver should call <b>WdfDeviceInitSetPowerNotPageable</b> if the driver is part of a driver stack that must not access pageable data during power transitions (such as the storage stack or the video stack), or if the driver is a bus driver that enumerates devices that might be storage or video devices. 

If your driver calls <b>WdfDeviceInitSetPowerNotPageable</b>, it must do so before it calls <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>.

For more information about calling <a href="wdf.wdfdevicecreate">WdfDeviceCreate</a>, see <a href="wdf.creating_a_framework_device_object">Creating a Framework Device Object</a>.

The following code example informs the power manager that a driver will not access pageable data while the system is transitioning between a sleeping state and the working (S0) state.

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
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt;= DISPATCH_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_childdeviceinitapi">ChildDeviceInitAPI</a>, <a href="devtest.kmdf_deviceinitapi">DeviceInitAPI</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_pdodeviceinitapi">PdoDeviceInitAPI</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfdeviceinitsetpowerpageable">WdfDeviceInitSetPowerPageable</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetPowerNotPageable method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
