---
UID: NE:wdfdevice._WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
title: "_WDF_POWER_POLICY_S0_IDLE_CAPABILITIES"
author: windows-driver-content
description: The WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.
old-location: wdf\wdf_power_policy_s0_idle_capabilities.htm
old-project: wdf
ms.assetid: b4a3611d-5eb6-4fb2-a66a-e563569c4790
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfdevice/IdleCapsInvalid, wdfdevice/IdleCannotWakeFromS0, IdleUsbSelectiveSuspend, wdfdevice/WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, wudfddi_types/IdleCannotWakeFromS0, wudfddi_types/IdleUsbSelectiveSuspend, DFDeviceObjectGeneralRef_42de97ef-91c2-44e1-9b69-fe92ca5b0edc.xml, wudfddi_types/IdleCapsInvalid, kmdf.wdf_power_policy_s0_idle_capabilities, IdleCanWakeFromS0, wdfdevice/IdleCanWakeFromS0, _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, IdleCannotWakeFromS0, wdfdevice/IdleUsbSelectiveSuspend, wudfddi_types/IdleCanWakeFromS0, wudfddi_types/WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, WDF_POWER_POLICY_S0_IDLE_CAPABILITIES, wdf.wdf_power_policy_s0_idle_capabilities, IdleCapsInvalid, WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration
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
-	wudfddi_types.h
apiname:
-	WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: WDF_POWER_POLICY_S0_IDLE_CAPABILITIES
req.product: Windows 10 or later.
---

# _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration identifies the capabilities that a device can support when it enters a low-power state while it is idling.

## Syntax
````
typedef enum _WDF_POWER_POLICY_S0_IDLE_CAPABILITIES { 
  IdleCapsInvalid          = 0,
  IdleCannotWakeFromS0     = 1,
  IdleCanWakeFromS0        = 2,
  IdleUsbSelectiveSuspend  = 3
} WDF_POWER_POLICY_S0_IDLE_CAPABILITIES;
````

## Constants

<table>
            
                <tr>
                    <td>IdleCannotWakeFromS0</td>
                    <td>The device cannot wake itself from a low-power state while the system is in its working (S0) state.</td>
                </tr>
            
                <tr>
                    <td>IdleCanWakeFromS0</td>
                    <td>The device can wake itself from a low-power state while the system is in its working (S0) state.</td>
                </tr>
            
                <tr>
                    <td>IdleCapsInvalid</td>
                    <td>For internal use only.</td>
                </tr>
            
                <tr>
                    <td>IdleUsbSelectiveSuspend</td>
                    <td>The device is connected to a USB bus and supports <a href="https://msdn.microsoft.com/library/windows/hardware/ff540144">USB selective suspend</a>. Use this value if your USB-connected device supports both idling and waking itself while the computer is in its working state. If your USB device supports only idling, use <b>IdleCannotWakeFromS0</b>. (Drivers for USB devices must not specify <b>IdleCanWakeFromS0</b>.) See the code examples in the following Examples section.

For Windows XP, the framework supports USB selective suspend only if the device's <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure shows that the device supports <a href="https://msdn.microsoft.com/b32375a9-0f34-474e-b3b9-7216b3d6665d">remote wakeup</a>. For Windows Vista and later versions of Windows, the framework supports USB selective suspend whether or not the device supports remote wakeup.</td>
                </tr>
</table>

## Remarks

The <b>WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</b> enumeration is used in the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 


#### Examples

The following code examples show how to enable idle support for a USB device. In each case, the STATUS_POWER_STATE_INVALID return value means the bus driver has reported that the device cannot wake itself.

<b>KMDF Example</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(&amp;idleSettings,
                                           IdleUsbSelectSuspend);
status = WdfDeviceAssignS0IdleSettings(device,
                                       &amp;idleSettings);
if (status == STATUS_POWER_STATE_INVALID){
    //
    // The device probably does not support wake. 
    // It might support idle without wake.
    //
    idleSettings.IdleCaps = IdleCannotWakeFromS0;
    status = WdfDeviceAssignS0IdleSettings(device,
                                           &amp;IdleSettings);
    if (!NT_SUCCESS(status) {...}
 }
else {...}</pre>
</td>
</tr>
</table></span></div>
<b>UMDF Example</b>

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>hr = pIWDFDevice2-&gt;AssignS0IdleSettings(IdleUsbSelectSuspend,
                                        PowerDeviceD3,
                                        IDLEWAKE_TIMEOUT_MSEC,
                                        IdleAllowUserControl,
                                        WdfTrue);
if (hr == HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)){
    //
    // The device probably does not support wake. 
    // It might support idle without wake.
    //
    hr = pIWDFDevice2-&gt;AssignS0IdleSettings(IdleCannotWakeFromS0,
                                         PowerDeviceD3,
                                         IDLEWAKE_TIMEOUT_MSEC,
                                         IdleAllowUserControl,
                                         WdfTrue);
    if (!SUCCEEDED(hr)) {...}
}
else {...}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 1.11 |
| **Header** | wdfdevice.h (include Wdf.h) |

## See Also

<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_POWER_POLICY_S0_IDLE_CAPABILITIES enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>