---
UID: NC:ntddk.SILO_MONITOR_CREATE_CALLBACK
title: SILO_MONITOR_CREATE_CALLBACK
author: windows-driver-content
description: This is callback is invoked when a new silo is created.
old-location: kernel\silo_monitor_create_callback.htm
old-project: kernel
ms.assetid: C26C5162-4BB0-401E-9AF5-AF1D2D8715F9
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.silo_monitor_create_callback, CreateCallback callback function [Kernel-Mode Driver Architecture], CreateCallback, SILO_MONITOR_CREATE_CALLBACK, SILO_MONITOR_CREATE_CALLBACK, ntddk/CreateCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
req.target-min-winversvr: Windows Server 2016
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ntddk.h
apiname:
-	CreateCallback
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---


# SILO_MONITOR_CREATE_CALLBACK callback function
This is callback is invoked when a new silo is created.

## Syntax

```
SILO_MONITOR_CREATE_CALLBACK SiloMonitorCreateCallback;

NTSTATUS SiloMonitorCreateCallback(
  PESILO Silo
)
{...}
```

## Parameters

`Silo`

The silo that was created.


## Return Value

The NT code returned by the operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |