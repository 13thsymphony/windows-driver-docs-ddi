---
UID: NA:mpiowmi
ms.assetid: d9d42961-f900-37a3-8d51-8325375dbe06
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Mpiowmi.h header



This header is used by Storage. For more information, see
- [Storage](../_storage/index.md)

Mpiowmi.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:----

# mpiowmi.h header



mpiowmi.h contains the following programming interfaces:







## Structures
| Title | Description |
| ---- |:---- |
| [_ClearMpioDiskHealthCounters_IN](ns-mpiowmi-_clearmpiodiskhealthcounters_in.md) | The ClearMpioDiskHealthCounters_IN structure is used to provide an input parameter to the ClearMpioDiskHealthCounters method. |
| [_ClearPathHealthCounters_IN](ns-mpiowmi-_clearpathhealthcounters_in.md) | The ClearPathHealthCounters_IN structure is used to provide an input parameter to the ClearPathHealthCounters method. |
| [_DSM_COUNTERS](ns-mpiowmi-_dsm_counters.md) | The DSM_COUNTERS structure holds the various timer counters that are applicable to all LUNs that are controlled by the DSM. |
| [_DSM_PARAMETERS](ns-mpiowmi-_dsm_parameters.md) | The DSM_PARAMETERS structure holds the DSM version and timer counters information. |
| [_DSM_VERSION](ns-mpiowmi-_dsm_version.md) | The DSM_VERSION structure represents version information that is associated with a DSM binary or package. |
| [_GetPathConfiguration_IN](ns-mpiowmi-_getpathconfiguration_in.md) | The GetPathConfiguration_IN structure is used to retrieve the per path device information. |
| [_GetPathConfiguration_OUT](ns-mpiowmi-_getpathconfiguration_out.md) | The GetPathConfiguration_OUT structure is used to report the output parameters that are associated with the GetPathConfiguration method. |
| [_MPIO_ADAPTER_INFORMATION](ns-mpiowmi-_mpio_adapter_information.md) | The MPIO_ADAPTER_INFORMATION structure contains information that pertains to MPIO's view of a path. |
| [_MPIO_CONTROLLER_CONFIGURATION](ns-mpiowmi-_mpio_controller_configuration.md) | The MPIO_CONTROLLER_CONFIGURATION structure provides a top-level view of the storage controllers and the targets that are connected to them in the system. |
| [_MPIO_CONTROLLER_INFO](ns-mpiowmi-_mpio_controller_info.md) | The MPIO_CONTROLLER_INFO structure represents a storage controller. |
| [_MPIO_DISK_HEALTH_CLASS](ns-mpiowmi-_mpio_disk_health_class.md) | The MPIO_DISK_HEALTH_CLASS structure contains the health information for a multi-path disk. |
| [_MPIO_DISK_HEALTH_INFO](ns-mpiowmi-_mpio_disk_health_info.md) | The MPIO_DISK_HEALTH_INFO structure is used to query the available health information for every multi-path disk in the system. |
| [_MPIO_DISK_INFO](ns-mpiowmi-_mpio_disk_info.md) | The MPIO_DISK_INFO structure allows applications to query the system for the top level view of its disk topology. The request must be directed to the MPIO control object by using its WMI instance name. |
| [_MPIO_DRIVE_INFO](ns-mpiowmi-_mpio_drive_info.md) | The MPIO_DRIVE_INFO structure represents a multi-path disk in the system. |
| [_MPIO_EventEntry](ns-mpiowmi-_mpio_evententry.md) | The MPIO_EventEntry structure is used to return events that MPIO has logged. |
| [_MPIO_PATH_HEALTH_CLASS](ns-mpiowmi-_mpio_path_health_class.md) | The MPIO_PATH_HEALTH_CLASS structure represents the health information for a path. |
| [_MPIO_PATH_HEALTH_INFO](ns-mpiowmi-_mpio_path_health_info.md) | The MPIO_PATH_HEALTH_INFO structure is used to query the available health information for every path that is exposed to the system. |
| [_MPIO_PATH_INFORMATION](ns-mpiowmi-_mpio_path_information.md) | The MPIO_PATH_INFORMATION structure represents a top-level view of all the paths that are under MPIO control. To query the path information, the request must be sent to the MPIO control object by using its WMI instance name. |
| [_MPIO_REGISTERED_DSM](ns-mpiowmi-_mpio_registered_dsm.md) | The MPIO_REGISTERED_DSM structure represents the top-level view of the registered DSMs on the system. To query this information, the request must be sent to the MPIO control object by using its WMI instance name. |
| [_MPIO_TIMERS_COUNTERS](ns-mpiowmi-_mpio_timers_counters.md) | The MPIO_TIMERS_COUNTERS structure controls the timer counters that affect all devices whose controlling DSMs do not implement independent timer counter settings. |
| [_MPIOMoveDevice_IN](ns-mpiowmi-_mpiomovedevice_in.md) | The MPIOMoveDevice_IN structure is used to set the active path on the device. |
| [_SCSI_ADDR](ns-mpiowmi-_scsi_addr.md) | The SCSI_ADDR structure represents a SCSI address. |
| [_SetDSMCounters_IN](ns-mpiowmi-_setdsmcounters_in.md) | The SetDSMCounters_IN structure is used to set the timer counters for a particular DSM. |