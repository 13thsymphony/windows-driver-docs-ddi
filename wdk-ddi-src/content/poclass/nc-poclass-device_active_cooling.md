---
UID : NC:poclass.DEVICE_ACTIVE_COOLING
title : DEVICE_ACTIVE_COOLING
author : windows-driver-content
description : The ActiveCooling callback routine engages or disengages a device's active-cooling function.
old-location : kernel\activecooling.htm
old-project : kernel
ms.assetid : ADC0145D-135F-46E6-91C9-B545DBE1D83B
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _PMI_THRESHOLD_CONFIGURATION, PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : poclass.h
req.include-header : Poclass.h
req.target-type : Desktop
req.target-min-winverclnt : Supported starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ActiveCooling
req.alt-loc : Poclass.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Called at PASSIVE_LEVEL.
req.typenames : PMI_THRESHOLD_CONFIGURATION, *PPMI_THRESHOLD_CONFIGURATION
---


# DEVICE_ACTIVE_COOLING function
The <i>ActiveCooling</i> callback routine engages or disengages a device's active-cooling function.

## Syntax

```
DEVICE_ACTIVE_COOLING DeviceActiveCooling;

void DeviceActiveCooling(
  PVOID Context,
  BOOLEAN Engaged
)
{...}
```

## Parameters

`Context`

A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="..\poclass\ns-poclass-_thermal_cooling_interface.md">THERMAL_COOLING_INTERFACE</a> structure that the driver previously supplied to the caller.

`Engaged`

Indicates whether to engage or disengage active cooling. If <b>TRUE</b>, the driver must engage active cooling (for example, by turning the fan on). If <b>FALSE</b>, the driver must disengage active cooling (for example, by turning the fan off).


## Return Value

None.

## Remarks

The driver for a device that has active-cooling capabilities can implement this routine to enable the operating system to engage or disengage the active-cooling function in the device.

For example, if the active-cooling function is a fan that can be turned on and off, the caller sets <i>Engaged</i> = <b>TRUE</b> to turn the fan on, and sets <i>Engaged</i> = <b>FALSE</b> to turn the fan off.

Initially, before the first call to the <i>ActiveCooling</i> routine, the active-cooling function in the device must be disengaged (for example, the fan must be turned off).

The driver for a device that does not have active-cooling capabilities should set the <b>ActiveCooling</b> member of the <b>THERMAL_COOLING_INTERFACE</b> structure to <b>NULL</b>.

For more information about active cooling, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh698271">Passive and Active Cooling Modes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | poclass.h (include Poclass.h) |
| **Library** |  |
| **IRQL** | Called at PASSIVE_LEVEL. |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\poclass\ns-poclass-_thermal_cooling_interface.md">THERMAL_COOLING_INTERFACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DEVICE_ACTIVE_COOLING routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>