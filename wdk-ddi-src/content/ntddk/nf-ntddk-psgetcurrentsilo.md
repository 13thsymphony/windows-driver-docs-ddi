---
UID : NF:ntddk.PsGetCurrentSilo
title : PsGetCurrentSilo function
author : windows-driver-content
description : This routine returns the current silo for the calling thread. First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.
old-location : kernel\psgetcurrentsilo.htm
old-project : kernel
ms.assetid : 535D7611-8C86-44CF-964C-731882A3AF69
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : PsGetCurrentSilo routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentsilo, PsGetCurrentSilo, ntddk/PsGetCurrentSilo
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
req.irql : "_IRQL_requires_max_(DISPATCH_LEVEL)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetCurrentSilo function
This routine returns the current silo for the calling thread.  First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.

## Syntax

````
PESILO PsGetCurrentSilo(void);
````

## Parameters

This function has no parameters.

## Return Value

A pointer to the <b>ESILO</b> object.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows 10, version 1607 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_IRQL_requires_max_(DISPATCH_LEVEL)" |