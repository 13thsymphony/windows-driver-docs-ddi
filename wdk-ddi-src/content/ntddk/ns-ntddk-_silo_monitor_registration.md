---
UID : NS:ntddk._SILO_MONITOR_REGISTRATION
title : "_SILO_MONITOR_REGISTRATION"
author : windows-driver-content
description : This structure specifies a server silo monitor that can receive notifications about server silo events.
old-location : kernel\silo_monitor_registration.htm
old-project : kernel
ms.assetid : F99F6346-3FEE-4889-A058-C7540A4CBFC8
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : ntddk/PSILO_MONITOR_REGISTRATION, kernel.silo_monitor_registration, SILO_MONITOR_REGISTRATION structure [Kernel-Mode Driver Architecture], ntddk/SILO_MONITOR_REGISTRATION, SILO_MONITOR_REGISTRATION, PSILO_MONITOR_REGISTRATION, _SILO_MONITOR_REGISTRATION, PSILO_MONITOR_REGISTRATION structure pointer [Kernel-Mode Driver Architecture], *PSILO_MONITOR_REGISTRATION
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10, version 1607
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : SILO_MONITOR_REGISTRATION, *PSILO_MONITOR_REGISTRATION
---

# _SILO_MONITOR_REGISTRATION structure
This structure specifies a server silo monitor that can receive notifications about server silo events.

## Syntax
````
typedef struct _SILO_MONITOR_REGISTRATION {
  UCHAR                           Version;
  BOOLEAN                         MonitorHost;
  BOOLEAN                         MonitorExistingSilos;
  UCHAR                           Reserved[5];
  UNION {
    PUNICODE_STRING DriverObjectName;
    PUNICODE_STRING ComponentName;
  }                          DUMMYUNIONNAME;
  SILO_MONITOR_CREATE_CALLBACK    CreateCallback;
  SILO_MONITOR_TERMINATE_CALLBACK TerminateCallback;
} SILO_MONITOR_REGISTRATION, *PSILO_MONITOR_REGISTRATION;
````

## Members


`CreateCallback`

A pointer to a callback that is invoked whenever a new server silo is created on the system.  This value may be <b>NULL</b>.  This gives drivers to opportunity to handle the event and set up per-silo data structures.

`MonitorExistingSilos`

If <b>true</b>, create and terminate notifications will be delivered for any silos that currently exist at the time of registration; otherwise, only notifications for new silos will be delivered.

`MonitorHost`

If <b>true</b>, a create notification will be delivered for the host context.

`Reserved`

Reserved for system use.

`TerminateCallback`

A pointer to a callback that is invoked whenever a server silo is terminated (about to be destroyed) on the system.  This value may be <b>NULL</b>.  This gives drivers the opportunity to complete work within the silo and begin tearing down their per-silo data structures.

`Version`

Set to <b>SERVER_SILO_MONITOR_REGISTRATION_VERSION</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |