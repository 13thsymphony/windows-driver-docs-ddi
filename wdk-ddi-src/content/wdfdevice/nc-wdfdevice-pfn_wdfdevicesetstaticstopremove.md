---
UID: NC:wdfdevice.PFN_WDFDEVICESETSTATICSTOPREMOVE
title: PFN_WDFDEVICESETSTATICSTOPREMOVE function
author: windows-driver-content
description: The WdfDeviceSetStaticStopRemove method informs the framework whether a device can be stopped and removed.
old-location: wdf\wdfdevicesetstaticstopremove.htm
old-project: wdf
ms.assetid: b2776618-2585-4a7a-9f8f-536f1d28745b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: PFN_WDFDEVICESETSTATICSTOPREMOVE
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
req.alt-api: WdfDeviceSetStaticStopRemove
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_DEVICE_SHUTDOWN_FLAGS
req.product: Windows 10 or later.
---

# PFN_WDFDEVICESETSTATICSTOPREMOVE function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetStaticStopRemove</b> method informs the framework whether a device can be stopped and removed.



## -syntax

````
VOID WdfDeviceSetStaticStopRemove(
  _In_ WDFDEVICE Device,
  _In_ BOOLEAN   Stoppable
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Stoppable [in]

A Boolean value that indicates whether the specified device can be stopped and removed. If <b>TRUE</b>, the device can be stopped and removed. If <b>FALSE</b>, the device cannot be stopped and removed.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
By default, a device can be stopped and removed. Therefore, a driver typically calls <b>WdfDeviceSetStaticStopRemove</b> only if it must temporarily set the <i>Stoppable</i> parameter to <b>FALSE</b>. For example, a driver that controls a DVD writer might call <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> before it begins burning a DVD. After the driver has finished burning the DVD, it would call <b>WdfDeviceSetStaticStopRemove</b> again with <i>Stoppable</i> set to <b>TRUE</b>.  

If your driver's device is supporting a special file (see <a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetspecialfilesupport.md">WdfDeviceSetSpecialFileSupport</a>), the framework will not allow the device to be stopped or removed. In this case, your driver does not have to call <b>WdfDeviceSetStaticStopRemove</b> .

The driver must match every call to <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> with a call to <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>TRUE</b>.

Calling <b>WdfDeviceSetStaticStopRemove</b> with <i>Stoppable</i> set to <b>FALSE</b> does not prevent the framework from notifying the driver if the device is unexpectedly removed (surprise-removed).

For more information about how to prevent the operating system from stopping a device, see <a href="https://msdn.microsoft.com/4c8f37b3-7961-4c78-a88b-3eec58155e66">Handling Requests to Stop a Device</a>.

The following code example informs the framework that the specified device cannot be stopped and removed.


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
Library

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
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>
</td>
</tr>
</table>