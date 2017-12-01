---
UID: NF.wdfdevice.WdfDeviceInitSetPnpPowerEventCallbacks
title: WdfDeviceInitSetPnpPowerEventCallbacks
author: windows-driver-content
description: The WdfDeviceInitSetPnpPowerEventCallbacks method registers a driver's Plug and Play and power management event callback functions.
old-location: wdf\wdfdeviceinitsetpnppowereventcallbacks.htm
old-project: wdf
ms.assetid: ace53515-0e8a-487d-abf7-caaa09478ed5
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WdfDeviceInitSetPnpPowerEventCallbacks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceInitSetPnpPowerEventCallbacks
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChildDeviceInitAPI, DeviceInitAPI, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2, PdoDeviceInitAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfDeviceInitSetPnpPowerEventCallbacks function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfDeviceInitSetPnpPowerEventCallbacks</b> method registers a driver's Plug and Play and power management event callback functions.</p>


## -syntax

````
VOID WdfDeviceInitSetPnpPowerEventCallbacks(
  _In_ PWDFDEVICE_INIT               DeviceInit,
  _In_ PWDF_PNPPOWER_EVENT_CALLBACKS PnpPowerEventCallbacks
);
````


## -parameters
<dl>

### -param <i>DeviceInit</i> [in]

<dd>
<p>A caller-supplied pointer to a <a href="wdf.wdfdevice_init">WDFDEVICE_INIT</a> structure.</p>
</dd>

### -param <i>PnpPowerEventCallbacks</i> [in]

<dd>
<p>A pointer to a caller-initialized <a href="..\wdfdevice\ns-wdfdevice--wdf-pnppower-event-callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>If your driver calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>, it must do so before it calls <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>.</p>

<p>For more information about calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>, see <a href="wdf.creating_a_framework_device_object">Creating a Framework Device Object</a>.</p>

<p>The following code example initializes a <a href="..\wdfdevice\ns-wdfdevice--wdf-pnppower-event-callbacks.md">WDF_PNPPOWER_EVENT_CALLBACKS</a> structure and then calls <b>WdfDeviceInitSetPnpPowerEventCallbacks</b>.</p>

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
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.kmdf_childdeviceinitapi">ChildDeviceInitAPI</a>, <a href="devtest.kmdf_deviceinitapi">DeviceInitAPI</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_drvackiostop">DrvAckIoStop</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_pdodeviceinitapi">PdoDeviceInitAPI</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdf-pnppower-event-callbacks-init.md">WDF_PNPPOWER_EVENT_CALLBACKS_INIT</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md">WdfDeviceInitSetPowerPolicyEventCallbacks</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceInitSetPnpPowerEventCallbacks method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
