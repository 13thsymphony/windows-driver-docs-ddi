---
UID: NF:ntddk.PsGetCurrentServerSilo
title: PsGetCurrentServerSilo function
author: windows-driver-content
description: This routine returns the effective server silo for the thread.
old-location: kernel\psgetcurrentserversilo.htm
old-project: kernel
ms.assetid: 4E30CD53-C078-40D7-BEF8-A39F57D71D42
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: PsGetCurrentServerSilo, PsGetCurrentServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentserversilo, ntddk/PsGetCurrentServerSilo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsGetCurrentServerSilo
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsGetCurrentServerSilo function
This routine returns the effective server silo for the thread.

## Syntax

```
NTKERNELAPI PESILO PsGetCurrentServerSilo(

);
```

## Parameters

This function has no parameters.

## Return Value

A pointer to the current server silo.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **IRQL** | "_IRQL_requires_max_(DISPATCH_LEVEL)" |