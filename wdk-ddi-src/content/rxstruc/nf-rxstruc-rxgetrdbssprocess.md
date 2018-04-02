---
UID: NF:rxstruc.RxGetRDBSSProcess
title: RxGetRDBSSProcess function
author: windows-driver-content
description: RxGetRDBSSProcess returns a pointer to the process of the main thread used by the RDBSS kernel process.
old-location: ifsk\rxgetrdbssprocess.htm
old-project: ifsk
ms.assetid: 2d3717c2-c809-48b9-a84b-1e69a04b767e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxGetRDBSSProcess, RxGetRDBSSProcess function [Installable File System Drivers], ifsk.rxgetrdbssprocess, rxref_7eee8a99-f7c3-41d3-8b16-1906ef301f47.xml, rxstruc/RxGetRDBSSProcess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxstruc.h
req.include-header: Rxstruc.h, Ntddk.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxstruc.h
api_name:
-	RxGetRDBSSProcess
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---


# RxGetRDBSSProcess function
<b>RxGetRDBSSProcess</b> returns a pointer to the process of the main thread used by the RDBSS kernel process.

## Syntax

```
PEPROCESS RxGetRDBSSProcess(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>RxGetRDBSSProcess</b> returns a pointer to the kernel process of the main thread used by RDBSS.

## Remarks

When <b>RxDriverEntry</b> is called to initialize RDBSS, a pointer to the kernel process that is running is retreived by calling <b>PsGetCurrentProcess</b> and stored in an internal RDBSS data structure. This value is returned when <b>RxGetRDBSSProcess</b> is called. This value is sometimes called the file system process.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxstruc.h (include Rxstruc.h, Ntddk.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559933">PsGetCurrentProcess</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554404">RxDriverEntry</a>