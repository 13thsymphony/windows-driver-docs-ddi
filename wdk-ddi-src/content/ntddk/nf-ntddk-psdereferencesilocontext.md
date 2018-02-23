---
UID: NF:ntddk.PsDereferenceSiloContext
title: PsDereferenceSiloContext function
author: windows-driver-content
description: This routine decrements the reference count on the object.
old-location: kernel\psdereferencesilocontext.htm
old-project: kernel
ms.assetid: B71C7E8F-E136-4C13-B771-03B3C3C1BE64
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ntddk/PsDereferenceSiloContext, PsDereferenceSiloContext, kernel.psdereferencesilocontext, PsDereferenceSiloContext routine [Kernel-Mode Driver Architecture]
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsDereferenceSiloContext
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---


# PsDereferenceSiloContext function
This routine decrements the reference count on the object.

## Syntax

````
void PsDereferenceSiloContext(
  _In_ PVOID SiloContext
);
````

## Parameters

`SiloContext`

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>.


## Return Value

This routine does not return a value.

## Remarks

If the reference count reaches zero it will call the cleanup callback provided when the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine created the object.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **Library** | NtosKrnl.exe |
| **IRQL** | "_IRQL_requires_max_(DISPATCH_LEVEL)" |