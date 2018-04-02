---
UID: NF:wdm.ExIsSoftBoot
title: ExIsSoftBoot function
author: windows-driver-content
description: Determines whether the system has gone through a soft restart.
old-location: kernel\exissoftboot.htm
old-project: kernel
ms.assetid: ff67bc75-b424-4278-b979-f67d118232aa
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExIsSoftBoot, ExIsSoftBoot function [Kernel-Mode Driver Architecture], kernel.exissoftboot, wdm/ExIsSoftBoot
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: "<=APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExIsSoftBoot
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExIsSoftBoot function
Determines whether the system has gone through a soft restart.

## Syntax

```
NTKERNELAPI BOOLEAN ExIsSoftBoot(

);
```

## Parameters

This function has no parameters.

## Return Value

TRUE indicates a soft restart; FALSE otherwise.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | wdm.h |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode) |
| **IRQL** | "<=APC_LEVEL" |