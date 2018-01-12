---
UID: NE:wdfdevice._WDF_POWER_DEVICE_STATE
title: _WDF_POWER_DEVICE_STATE
author: windows-driver-content
description: The WDF_POWER_DEVICE_STATE enumeration identifies the device power states that a device might support.
old-location: wdf\wdf_power_device_state.htm
old-project: wdf
ms.assetid: 66ff00fd-43b0-4fe1-a010-4b5ef65fa811
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _WDF_POWER_DEVICE_STATE, WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_POWER_DEVICE_STATE
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE
req.product: Windows 10 or later.
---

# _WDF_POWER_DEVICE_STATE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_DEVICE_STATE</b> enumeration identifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff543162">device power states</a> that a device might support.



## -syntax

````
typedef enum _WDF_POWER_DEVICE_STATE { 
  WdfPowerDeviceInvalid                = 0,
  WdfPowerDeviceD0                     = 1,
  WdfPowerDeviceD1                     = 2,
  WdfPowerDeviceD2                     = 3,
  WdfPowerDeviceD3                     = 4,
  WdfPowerDeviceD3Final                = 5,
  WdfPowerDevicePrepareForHibernation  = 6,
  WdfPowerDeviceMaximum                = 7
} WDF_POWER_DEVICE_STATE, *PWDF_POWER_DEVICE_STATE;
````


## -enum-fields

### -field WdfPowerDeviceInvalid

The device power state is invalid or unknown.


### -field WdfPowerDeviceD0

The D0 device power state.


### -field WdfPowerDeviceD1

The D1 device power state.


### -field WdfPowerDeviceD2

The D2 device power state.


### -field WdfPowerDeviceD3

The D3 device power state.


### -field WdfPowerDeviceD3Final

Represents the final time that the device enters the D3 device power state. Typically, this enumerator means that the system is being turned off, the device is about to be removed, or a <a href="wdf.the_pnp_manager_redistributes_system_resources">resource rebalance</a> is in progress. The device might have been already removed.


### -field WdfPowerDevicePrepareForHibernation

The device supports hibernation files, and the system is ready to hibernate by entering <a href="https://msdn.microsoft.com/2fd883b5-4e89-4ce9-b75a-b821348ac860">system state S4</a>. The driver must not turn off the device. For more information, see <a href="https://msdn.microsoft.com/350e715f-be36-4999-99a2-6175d9763b3f">Supporting Special Files</a>.


### -field WdfPowerDeviceMaximum

The maximum enumerator value for this enumeration.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_exit.md">EvtDeviceD0Exit</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_DEVICE_STATE enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

