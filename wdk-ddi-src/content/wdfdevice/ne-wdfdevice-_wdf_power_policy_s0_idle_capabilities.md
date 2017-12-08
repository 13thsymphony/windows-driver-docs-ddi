---
UID: NE.wdfdevice._WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
title: _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
author: windows-driver-content
description: The WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.
old-location: wdf\wdf_power_policy_s0_idle_capabilities.htm
old-project: wdf
ms.assetid: b4a3611d-5eb6-4fb2-a66a-e563569c4790
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 1.11
req.alt-api: WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
req.alt-loc: wdfdevice.h,wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.


## -syntax

````
typedef enum _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES { 
  IdleCapsInvalid          = 0,
  IdleCannotWakeFromS0     = 1,
  IdleCanWakeFromS0        = 2,
  IdleUsbSelectiveSuspend  = 3
} WDF_POWER_POLICY_S0_IDLE_CAPABILITIES;
````


## -enum-fields

### -field IdleCapsInvalid

For internal use only.

### -field IdleCannotWakeFromS0

The device cannot wake itself from a low-power state while the system is in its working (S0) state.

### -field IdleCanWakeFromS0

The device can wake itself from a low-power state while the system is in its working (S0) state.

### -field IdleUsbSelectiveSuspend

The device is connected to a USB bus and supports <a href="buses.usb_selective_suspend">USB selective suspend</a>. Use this value if your USB-connected device supports both idling and waking itself while the computer is in its working state. If your USB device supports only idling, use <b>IdleCannotWakeFromS0</b>. (Drivers for USB devices must not specify <b>IdleCanWakeFromS0</b>.) See the code examples in the following Examples section.
For Windows XP, the framework supports USB selective suspend only if the device's <a href="buses.usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure shows that the device supports <a href="buses.remote_wakeup_of_usb_devices">remote wakeup</a>. For Windows Vista and later versions of Windows, the framework supports USB selective suspend whether or not the device supports remote wakeup.

## -remarks
The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration is used in the <a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 

The following code examples show how to enable idle support for a USB device. In each case, the STATUS_POWER_STATE_INVALID return value means the bus driver has reported that the device cannot wake itself.

<b>KMDF Example</b>

<b>UMDF Example</b>

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
1.11
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h); </dt>
<dt>Wudfddi_types.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
