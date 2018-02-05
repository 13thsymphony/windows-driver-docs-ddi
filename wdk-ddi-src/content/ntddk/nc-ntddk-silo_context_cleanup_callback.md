---
UID : NC:ntddk.SILO_CONTEXT_CLEANUP_CALLBACK
title : SILO_CONTEXT_CLEANUP_CALLBACK
author : windows-driver-content
description : This callback is invoked when the context object reaches a reference count of zero.
old-location : kernel\silo_context_cleanup_callback.htm
old-project : kernel
ms.assetid : 452E63E8-DFBB-43AF-81F4-0405C3EF74CE
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.silo_context_cleanup_callback, CleanupCallback callback function [Kernel-Mode Driver Architecture], CleanupCallback, SILO_CONTEXT_CLEANUP_CALLBACK, SILO_CONTEXT_CLEANUP_CALLBACK, ntddk/CleanupCallback
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PFILTER_INITIALIZATION_DATA, FILTER_INITIALIZATION_DATA"
---


# SILO_CONTEXT_CLEANUP_CALLBACK callback function
This callback is invoked when the context object reaches a reference count of zero.

## Syntax

```
SILO_CONTEXT_CLEANUP_CALLBACK SiloContextCleanupCallback;

void SiloContextCleanupCallback(
  PVOID SiloContext
)
{...}
```

## Parameters

`SiloContext`

A pointer provided by the user with the call to <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a>.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |