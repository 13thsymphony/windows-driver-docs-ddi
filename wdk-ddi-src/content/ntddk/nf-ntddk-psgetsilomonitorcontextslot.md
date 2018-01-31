---
UID : NF:ntddk.PsGetSiloMonitorContextSlot
title : PsGetSiloMonitorContextSlot function
author : windows-driver-content
description : This routine returns the silo context slot that was allocated by the monitor during the registration.
old-location : kernel\psgetsilomonitorcontextslot.htm
old-project : kernel
ms.assetid : 0871EA8C-4F59-451E-89FB-8A0D44219456
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsGetSiloMonitorContextSlot, PsGetSiloMonitorContextSlot routine [Kernel-Mode Driver Architecture], ntddk/PsGetSiloMonitorContextSlot, kernel.psgetsilomonitorcontextslot
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetSiloMonitorContextSlot function
This routine returns the silo context slot that was allocated by the monitor during the registration.

## Syntax

````
ULONG PsGetSiloMonitorContextSlot(
  _In_ PSILO_MONITOR Monitor
);
````

## Parameters

`Monitor`

A pointer to the silo monitor.


## Return Value

A valid silo context slot.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |