---
UID: NA:poclass
ms.assetid: e8e59bde-a107-30c0-9d4b-dd962feae2e4
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Poclass.h header



This header is used by Battery, Windows kernel. For more information, see
- [Battery](../_battery/index.md)
- [Windows kernel](../_kernel/index.md)

Poclass.h contain these programming interfaces:


## Callback functions

| Title   | Description   |
| ---- |:---- |
| [DEVICE_ACTIVE_COOLING callback](nc-poclass-device_active_cooling.md) | The ActiveCooling callback routine engages or disengages a device's active-cooling function. |
| [DEVICE_PASSIVE_COOLING callback](nc-poclass-device_passive_cooling.md) | The PassiveCooling callback routine controls the degree to which the device must throttle its performance to meet cooling requirements. |

## Structures

| Title   | Description   |
| ---- |:----

# poclass.h header



poclass.h contains the following programming interfaces:






## Callback functions
| Title | Description |
| ---- |:---- |
| [DEVICE_ACTIVE_COOLING](nc-poclass-device_active_cooling.md) | The ActiveCooling callback routine engages or disengages a device's active-cooling function. |
| [DEVICE_PASSIVE_COOLING](nc-poclass-device_passive_cooling.md) | The PassiveCooling callback routine controls the degree to which the device must throttle its performance to meet cooling requirements. |


## Structures
| Title | Description |
| ---- |:---- |
| [_BATTERY_INFORMATION](ns-poclass-_battery_information.md) | Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests. |
| [_BATTERY_MANUFACTURE_DATE](ns-poclass-_battery_manufacture_date.md) | Battery miniclass drivers fill in this structure in response to certain BatteryMiniQueryInformation requests. |
| [_BATTERY_STATUS](ns-poclass-_battery_status.md) | The BATTERY_STATUS structure is used by battery miniclass drivers to return status information in response to a call to BatteryMiniQueryStatus. |
| [_THERMAL_COOLING_INTERFACE](ns-poclass-_thermal_cooling_interface.md) | The THERMAL_COOLING_INTERFACE structure enables the operating system to control the thermal management settings of a device. |