---
UID: NF:ntddk.PsReferenceSiloContext
title: PsReferenceSiloContext function
author: windows-driver-content
description: This routine increments the reference count on the object.
old-location: kernel\psreferencesilocontext.htm
old-project: kernel
ms.assetid: 04867D53-DB36-482A-93BF-C91D13998B3F
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: PsReferenceSiloContext, PsReferenceSiloContext routine [Kernel-Mode Driver Architecture], kernel.psreferencesilocontext, ntddk/PsReferenceSiloContext
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
-	PsReferenceSiloContext
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# PsReferenceSiloContext function
This routine increments the reference count on the object.

## Syntax

````
void PsReferenceSiloContext(
  _In_ PVOID SiloContext
);
````

## Parameters

`SiloContext`

A pointer to the object created by the <a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a> routine. This parameter is required and it cannot be <b>NULL</b>.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1607 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | ntddk.h |
| **IRQL** | "_IRQL_requires_max_(DISPATCH_LEVEL)" |

## See Also

<a href="..\ntddk\nf-ntddk-pscreatesilocontext.md">PsCreateSiloContext</a>