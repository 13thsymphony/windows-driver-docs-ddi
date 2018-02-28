---
UID: NC:ntddk.SILO_MONITOR_TERMINATE_CALLBACK
title: SILO_MONITOR_TERMINATE_CALLBACK
author: windows-driver-content
description: This callback is invoked when a silo is terminated.
old-location: kernel\silo_monitor_terminate_callback.htm
old-project: kernel
ms.assetid: 1F87D6AC-3603-4A34-BAAB-8B43ADF9E595
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: SILO_MONITOR_TERMINATE_CALLBACK, TerminateCallback, TerminateCallback callback function [Kernel-Mode Driver Architecture], kernel.silo_monitor_terminate_callback, ntddk/TerminateCallback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ntddk.h
api_name:
-	TerminateCallback
product: Windows
targetos: Windows
req.typenames: FILTER_INITIALIZATION_DATA, *PFILTER_INITIALIZATION_DATA
---


# SILO_MONITOR_TERMINATE_CALLBACK callback function
This callback is invoked when a silo is terminated.

## Syntax

```
SILO_MONITOR_TERMINATE_CALLBACK SiloMonitorTerminateCallback;

void SiloMonitorTerminateCallback(
  PESILO Silo
)
{...}
```

## Parameters

`Silo`

The silo to be terminated.


## Return Value

This callback function does not return a value.

## Remarks

The expected behavior is that the component will drop any outstanding silo references.  A driver may no longer operate within the namespace of a silo (via <a href="..\ntddk\nf-ntddk-psattachsilotocurrentthread.md">PsAttachSiloToCurrentThread</a>) once it has returned from this function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |