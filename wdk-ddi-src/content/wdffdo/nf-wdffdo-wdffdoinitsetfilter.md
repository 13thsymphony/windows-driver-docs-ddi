---
UID: NF:wdffdo.WdfFdoInitSetFilter
title: WdfFdoInitSetFilter function
author: windows-driver-content
description: The WdfFdoInitSetFilter method identifies the calling driver as an upper-level or lower-level filter driver, for a specified device.
old-location: wdf\wdffdoinitsetfilter.htm
old-project: wdf
ms.assetid: 6e195025-4e70-44fa-a12d-0a98417381a0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectFdoPdoRef_d1040c41-d94a-489d-ab74-9b3ae1e900bb.xml, WdfFdoInitSetFilter, WdfFdoInitSetFilter method, kmdf.wdffdoinitsetfilter, wdf.wdffdoinitsetfilter, wdffdo/WdfFdoInitSetFilter
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfFdoInitSetFilter
product: Windows
targetos: Windows
req.typenames: WDF_DRIVER_VERSION_AVAILABLE_PARAMS, *PWDF_DRIVER_VERSION_AVAILABLE_PARAMS
req.product: Windows 10 or later.
---


# WdfFdoInitSetFilter function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfFdoInitSetFilter</b> method identifies the calling driver as an upper-level or lower-level <a href="https://msdn.microsoft.com/4def5503-bb0e-4bae-b048-4c8d25d62020">filter driver</a>, for a specified device.

## Syntax

```
void WdfFdoInitSetFilter(
  PWDFDEVICE_INIT DeviceInit
);
```

## Parameters

`DeviceInit`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure that the driver obtained from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.


## Return Value

None

## Remarks

Filter drivers typically process some I/O requests, but they simply pass most requests to the next driver in the driver stack. If the framework receives a request for one of your driver's devices, and if the driver has not created an I/O queue to receive requests that match the request type, the way the framework processes the request depends on whether the driver has called <b>WdfFdoInitSetFilter</b>:

<ul>
<li>
If a driver calls <b>WdfFdoInitSetFilter</b>, the driver framework forwards the request to the next driver.

</li>
<li>
If a driver does not call <b>WdfFdoInitSetFilter</b>, the framework completes the request with a status value of STATUS_INVALID_DEVICE_REQUEST.

</li>
</ul>
If a driver calls <b>WdfFdoInitSetFilter</b>, it should not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff546128">WdfDeviceInitSetIoType</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff546142">WdfDeviceInitSetPowerInrush</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff546766">WdfDeviceInitSetPowerPageable</a> because the framework ignores the information provided by these calls. Instead, the framework obtains this information from the next-lower device object in the driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/wdm-concepts-for-kmdf-drivers">device stack</a>.

The driver must call <b>WdfFdoInitSetFilter</b> before calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>. For more information about calling <b>WdfDeviceCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-a-framework-device-object">Creating a Framework Device Object</a>. In addition, the driver must call <b>WdfFdoInitSetFilter</b> before returning from its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function.

For more information about <b>WdfFdoInitSetFilter</b>, see <a href="https://msdn.microsoft.com/f5a4851d-7caf-467d-9500-11f341fdf680">Creating Device Objects in a Filter Driver</a>, <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a> and <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example identifies the calling driver as a filter driver for the specified device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WdfFdoInitSetFilter(DeviceInit);</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdffdo.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | DeviceInitAPI, DriverCreate, DrvAckIoStop, KmdfIrql, KmdfIrql2 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>