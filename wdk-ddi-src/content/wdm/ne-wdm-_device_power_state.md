---
UID: NE:wdm._DEVICE_POWER_STATE
title: "_DEVICE_POWER_STATE"
author: windows-driver-content
description: The DEVICE_POWER_STATE enumeration type indicates a device power state.
old-location: kernel\device_power_state.htm
old-project: kernel
ms.assetid: d3166685-2aec-4874-a5a9-8cc293a96a2c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: wdm/PowerDeviceD1, PowerDeviceD2, wdm/PowerDeviceD2, wdm/PDEVICE_POWER_STATE, *PDEVICE_POWER_STATE, DEVICE_POWER_STATE, PowerDeviceUnspecified, PowerDeviceD0, wdm/PowerDeviceD0, wdm/PowerDeviceD3, PDEVICE_POWER_STATE enumeration pointer [Kernel-Mode Driver Architecture], wdm/PowerDeviceUnspecified, wdm/PowerDeviceMaximum, _DEVICE_POWER_STATE, PowerDeviceMaximum, PowerDeviceD1, kernel.device_power_state, wdm/DEVICE_POWER_STATE, sysenum_4f65cc59-f3a2-42ef-a8bb-7a2d178a6be7.xml, PDEVICE_POWER_STATE, DEVICE_POWER_STATE enumeration [Kernel-Mode Driver Architecture], PowerDeviceD3
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdm.h
apiname:
-	DEVICE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: "*PDEVICE_POWER_STATE, DEVICE_POWER_STATE"
req.product: Windows 10 or later.
---

# _DEVICE_POWER_STATE Enumeration
The <b>DEVICE_POWER_STATE</b> enumeration type indicates a <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a>.

## Syntax
````
typedef enum _DEVICE_POWER_STATE { 
  PowerDeviceUnspecified  = 0,
  PowerDeviceD0           = 1,
  PowerDeviceD1           = 2,
  PowerDeviceD2           = 3,
  PowerDeviceD3           = 4,
  PowerDeviceMaximum      = 5
} DEVICE_POWER_STATE, *PDEVICE_POWER_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>PowerDeviceD0</td>
                    <td>Indicates a maximum device power state, which corresponds to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543210">device working state D0</a>.</td>
                </tr>
            
                <tr>
                    <td>PowerDeviceD1</td>
                    <td>Indicates a <a href="https://msdn.microsoft.com/f594a63f-10ce-439d-abe3-d342555d98f0">device sleeping state</a> less than <b>PowerDeviceD0</b> and greater than <b>PowerDeviceD2</b>, which corresponds to device power state D1.</td>
                </tr>
            
                <tr>
                    <td>PowerDeviceD2</td>
                    <td>Indicates a device sleeping state less than <b>PowerDeviceD1</b> and greater than <b>PowerDeviceD3</b>, which corresponds to device power state D2.</td>
                </tr>
            
                <tr>
                    <td>PowerDeviceD3</td>
                    <td>Indicates the lowest-powered device sleeping state, which corresponds to device power state D3.</td>
                </tr>
            
                <tr>
                    <td>PowerDeviceMaximum</td>
                    <td>The number of device power state values for this enumeration type that represent actual power states. The value of the other device power states is less than this value.</td>
                </tr>
            
                <tr>
                    <td>PowerDeviceUnspecified</td>
                    <td>Indicates an unspecified device power state.</td>
                </tr>
</table>

    ## Remarks

        A power state indicates the level of power consumption—and thus the extent of computing activity—by the system or by a single device. The power manager sets the power state of the system as a whole, where the system power state is indicated by one of the values of the <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a> enumeration type. Device drivers set the power state of their individual devices, where the device power state is indicated by one of the values of the <b>DEVICE_POWER_STATE</b> enumeration type.

For more information about system power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff546941">Handling System Power State Requests</a>. For more information about device power states, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554397">Managing Power for Individual Devices</a>. For more information about power management in general, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff548108">Introduction to Power Management</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h) |

    ## See Also

        <a href="..\wdm\ne-wdm-_system_power_state.md">SYSTEM_POWER_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_POWER_STATE enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>