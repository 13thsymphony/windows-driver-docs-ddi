---
UID: NF:dbgeng.DebugCommandException
title: DebugCommandException function
author: windows-driver-content
description: Specifies a debug command exception.
old-location: debugger\debugcommandexception.htm
old-project: debugger
ms.assetid: 6DC67840-B985-45D0-8E81-671C3DC1EBC2
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DebugCommandException, DebugCommandException function [Windows Debugging], dbgeng/DebugCommandException, debugger.debugcommandexception
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: dbgeng.h
req.include-header: Dbgeng.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dbgeng.h
api_name:
-	DebugCommandException
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# DebugCommandException function
Specifies a debug command exception.

## Syntax

````
void WINAPI DebugCommandException(
   ULONG Command,
   ULONG ArgSize,
   PVOID Arg
);
````

## Parameters

`Command`

A command.

`ArgSize`

The size of the argument.

`Arg`

A pointer to an argument.


## Return Value

This function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | NtosKrnl.exe |