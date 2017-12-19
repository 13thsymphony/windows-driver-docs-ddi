---
UID: NE.wdfdevice._WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
title: _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
author: windows-driver-content
description: The WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.
old-location: wdf\wdf_power_policy_s0_idle_user_control.htm
old-project: wdf
ms.assetid: ee51c436-2d1c-49d0-ab76-337317eeeeda
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL, WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
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
req.alt-api: WDF_POWER_POLICY_S0_IDLE_USER_CONTROL
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

# _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration identifies whether a user can control a device's behavior when the device is idle and the system is in its working (S0) state.



## -syntax

````
typedef enum _WDF_POWER_POLICY_S0_IDLE_USER_CONTROL { 
  IdleUserControlInvalid     = 0,
  IdleDoNotAllowUserControl  = 1,
  IdleAllowUserControl       = 2
} WDF_POWER_POLICY_S0_IDLE_USER_CONTROL;
````


## -enum-fields

### -field IdleUserControlInvalid

For internal use only.


### -field IdleDoNotAllowUserControl

Users cannot control the device's idle behavior.


### -field IdleAllowUserControl

Users can control the device's idle behavior.


## -remarks
The <b>WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</b> enumeration is used as a member type in the <a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

Users control a device's idle behavior by modifying information on a <a href="wdf.user_control_of_device_idle_and_wake_behavior">property sheet</a>. The framework creates the property sheet and Device Manager displays it.


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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_S0_IDLE_USER_CONTROL enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

