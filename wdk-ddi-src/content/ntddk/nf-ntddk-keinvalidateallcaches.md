---
UID: NF:ntddk.KeInvalidateAllCaches
title: KeInvalidateAllCaches function
author: windows-driver-content
description: The KeInvalidateAllCaches routine flushes all processor caches.
old-location: kernel\keinvalidateallcaches.htm
old-project: kernel
ms.assetid: a7971cd1-1e9b-4d81-8422-1ee36651973a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: KeInvalidateAllCaches routine [Kernel-Mode Driver Architecture], KeInvalidateAllCaches, ntddk/KeInvalidateAllCaches, k105_4b59c5bd-70e3-48e1-aa6c-abf4e02925e8.xml, kernel.keinvalidateallcaches
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
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
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInvalidateAllCaches
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# KeInvalidateAllCaches function
The <b>KeInvalidateAllCaches</b> routine flushes all processor caches.

## Syntax

````
BOOLEAN KeInvalidateAllCaches(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeInvalidateAllCaches</b> returns a value that is reserved for system use. Treat this value as VOID.

## Remarks

The <b>KeInvalidateAllCaches</b> routine flushes each processor's caches and marks each cache's contents invalid. The processor caches are guaranteed to have completed the flush operation before <b>KeInvalidateAllCaches</b> returns.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |