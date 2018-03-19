---
UID: NF:wdfdevice.WdfDeviceSetPowerCapabilities
title: WdfDeviceSetPowerCapabilities function
author: windows-driver-content
description: The WdfDeviceSetPowerCapabilities method reports a device's power capabilities.
old-location: wdf\wdfdevicesetpowercapabilities.htm
old-project: wdf
ms.assetid: e04558e3-a95a-408b-961b-e8ea7ac9136d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFDeviceObjectGeneralRef_d3d51bfe-62da-4146-b4c1-152cac9f0e82.xml, WdfDeviceSetPowerCapabilities, WdfDeviceSetPowerCapabilities method, kmdf.wdfdevicesetpowercapabilities, wdf.wdfdevicesetpowercapabilities, wdfdevice/WdfDeviceSetPowerCapabilities
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfDeviceSetPowerCapabilities
product: Windows
targetos: Windows
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---


# WdfDeviceSetPowerCapabilities function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceSetPowerCapabilities</b> method reports a device's power capabilities.

## Syntax

````
VOID WdfDeviceSetPowerCapabilities(
  _In_ WDFDEVICE                      Device,
  _In_ PWDF_DEVICE_POWER_CAPABILITIES PowerCapabilities
);
````

## Parameters

`Device`

A handle to a framework device object.

`PowerCapabilities`

A pointer to a driver-allocated <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

A driver typically calls <b>WdfDeviceSetPowerCapabilities</b> from within one of the following callback functions:

<ul>
<li>

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>


</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a> (if the <i>PreviousState</i> parameter's value is <b>WdfPowerDeviceD3Final</b>) 

</li>
<li>

<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>


</li>
<li>

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>


</li>
</ul>
If more than one driver in the device's driver stack call <b>WdfDeviceSetPowerCapabilities</b>, the power manager uses the values that are supplied by the driver that is highest in the stack.


#### Examples

The following code example initializes a WDF_DEVICE_POWER_CAPABILITIES structure and then calls <b>WdfDeviceSetPowerCapabilities</b>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_CAPABILITIES powerCaps;

WDF_DEVICE_POWER_CAPABILITIES_INIT(&amp;powerCaps);
powerCaps.DeviceD1 = WdfTrue;
powerCaps.WakeFromD1 = WdfTrue;
powerCaps.DeviceWake = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemWorking] = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemSleeping1] = PowerDeviceD1;
powerCaps.DeviceState[PowerSystemSleeping2] = PowerDeviceD2;
powerCaps.DeviceState[PowerSystemSleeping3] = PowerDeviceD2;
powerCaps.DeviceState[PowerSystemHibernate] = PowerDeviceD3;
powerCaps.DeviceState[PowerSystemShutdown] = PowerDeviceD3;

WdfDeviceSetPowerCapabilities(
                              device,
                              &amp;powerCaps
                              );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |
| **Library** | Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF) |
| **IRQL** | "<=DISPATCH_LEVEL" |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicesetpnpcapabilities.md">WdfDeviceSetPnpCapabilities</a>



<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a>



<a href="..\wdfdevice\nf-wdfdevice-wdf_device_power_capabilities_init.md">WDF_DEVICE_POWER_CAPABILITIES_INIT</a>