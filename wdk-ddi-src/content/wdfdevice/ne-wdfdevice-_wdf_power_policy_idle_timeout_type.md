---
UID: NE:wdfdevice._WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE
title: "_WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE"
author: windows-driver-content
description: The WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration identifies how the idle timeout for a device is determined.
old-location: wdf\wdf_power_policy_idle_timeout_type.htm
old-project: wdf
ms.assetid: CFB7E2EA-22D9-4181-B773-BC5691B28CFD
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration pointer, wdfdevice/SystemManagedIdleTimeout, *PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, wdfdevice/SystemManagedIdleTimeoutWithHint, SystemManagedIdleTimeout, kmdf.wdf_power_policy_idle_timeout_type, SystemManagedIdleTimeoutWithHint, WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration, wdfdevice/DriverManagedIdleTimeout, wdfdevice/PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, DriverManagedIdleTimeout, wdfdevice/WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, _WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, wdf.wdf_power_policy_idle_timeout_type
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfdevice.h
apiname:
-	WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE
product: Windows
targetos: Windows
req.typenames: "*PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE"
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]


   The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</b> enumeration identifies how the idle timeout for a device is determined.

## Syntax
````
typedef enum _WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE { 
  DriverManagedIdleTimeout          = 0,
  SystemManagedIdleTimeout          = 1,
  SystemManagedIdleTimeoutWithHint  = 2
} WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE, *PWDF_POWER_POLICY_IDLE_TIMEOUT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>DriverManagedIdleTimeout</td>
                    <td>The idle timeout value is determined by the <b>IdleTimeout</b> member of the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.</td>
                </tr>
            
                <tr>
                    <td>SystemManagedIdleTimeout</td>
                    <td>Starting in Windows 8, the timeout value is determined by the power framework (PoFx). The value of the <b>IdleTimeout</b> member is not used.

On operating systems earlier than Windows 8, the behavior is same as <b>DriverManagedIdleTimeout</b>.</td>
                </tr>
            
                <tr>
                    <td>SystemManagedIdleTimeoutWithHint</td>
                    <td>Starting in Windows 8, the PoFx uses the value specified in the <b>IdleTimeout</b> member as an input when determining at what point after all the components are idle to transition the device to a low-power (Dx) state. This option enables the driver to delay the transition to a low-power state.

Typically, PoFx waits until the end of the time-out interval to initiate the power transition. However, if PoFx is preparing to enter a low-power system state, PoFx might end the time-out interval early.

The  <b>IdleTimeout</b> value is only advisory. The actual duration after which the PoFx allows the device to enter a low-power state might be greater than or less than the <b>IdleTimeout</b> value.

On operating systems earlier than Windows 8, the behavior is the same as <b>DriverManagedIdleTimeout</b>.</td>
                </tr>
</table>

    ## Remarks

        The <b>WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE</b> enumeration is used in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.11 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfdevice.h (include Wdf.h) |

    ## See Also

        <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>