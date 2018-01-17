---
UID: NF:wdffdo.WdfFdoInitSetFilter
title: WdfFdoInitSetFilter function
author: windows-driver-content
description: The WdfFdoInitSetFilter method identifies the calling driver as an upper-level or lower-level filter driver, for a specified device.
old-location: wdf\wdffdoinitsetfilter.htm
old-project: wdf
ms.assetid: 6e195025-4e70-44fa-a12d-0a98417381a0
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfFdoInitSetFilter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdffdo.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfFdoInitSetFilter
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DeviceInitAPI, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS, WDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---

# WdfFdoInitSetFilter function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFdoInitSetFilter</b> method identifies the calling driver as an upper-level or lower-level <a href="https://msdn.microsoft.com/4def5503-bb0e-4bae-b048-4c8d25d62020">filter driver</a>, for a specified device.



## -syntax

````
VOID WdfFdoInitSetFilter(
  _In_ PWDFDEVICE_INIT DeviceInit
);
````


## -parameters

### -param DeviceInit [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.


## -returns
None


## -remarks
Filter drivers typically process some I/O requests, but they simply pass most requests to the next driver in the driver stack. If the framework receives a request for one of your driver's devices, and if the driver has not created an I/O queue to receive requests that match the request type, the way the framework processes the request depends on whether the driver has called <b>WdfFdoInitSetFilter</b>:

If a driver calls <b>WdfFdoInitSetFilter</b>, the driver framework forwards the request to the next driver.

If a driver does not call <b>WdfFdoInitSetFilter</b>, the framework completes the request with a status value of STATUS_INVALID_DEVICE_REQUEST.

If a driver calls <b>WdfFdoInitSetFilter</b>, it should not call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetiotype.md">WdfDeviceInitSetIoType</a>, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerinrush.md">WdfDeviceInitSetPowerInrush</a>, or <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceinitsetpowerpageable.md">WdfDeviceInitSetPowerPageable</a> because the framework ignores the information provided by these calls. Instead, the framework obtains this information from the next-lower device object in the driver's <a href="wdf.wdm_concepts_for_kmdf_drivers#device_stacks#device_stacks">device stack</a>.

The driver must call <b>WdfFdoInitSetFilter</b> before calling <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://msdn.microsoft.com/25023c19-a153-4bd4-9fb6-3a1bf85860aa">Creating a Framework Device Object</a>. In addition, the driver must call <b>WdfFdoInitSetFilter</b> before returning from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function.

For more information about <b>WdfFdoInitSetFilter</b>, see <a href="https://msdn.microsoft.com/f5a4851d-7caf-467d-9500-11f341fdf680">Creating Device Objects in a Filter Driver</a>, <a href="https://msdn.microsoft.com/03b09c94-6b72-4234-b21f-203f93b7a2e8">Creating I/O Queues</a> and <a href="https://msdn.microsoft.com/75e007e3-1b97-44db-ac86-56aab78222a6">Forwarding I/O Requests</a>.

The following code example identifies the calling driver as a filter driver for the specified device.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfFdoInitSetFilter method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

