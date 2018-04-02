---
UID: NF:wdbgexts.GetPebAddress
title: GetPebAddress function
author: windows-driver-content
description: The GetPebAddress function returns the address of the process environment block (PEB) for a system process.
old-location: debugger\getpebaddress.htm
old-project: debugger
ms.assetid: 314eb897-a441-41c7-8b74-a853de70e066
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetPebAddress, GetPebAddress function [Windows Debugging], WdbgExts_Ref_a51cb865-4701-4fbc-a075-7bcadd8ee8be.xml, debugger.getpebaddress, wdbgexts/GetPebAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdbgexts.h
api_name:
-	GetPebAddress
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# GetPebAddress function
The <b>GetPebAddress</b> function returns the address of the process environment block (PEB) for a system process.

## Syntax

```
void GetPebAddress(
  ULONG64    CurrentThread,
  PULONGLONG Address
);
```

## Parameters

`CurrentThread`

Specifies an operating system thread whose PEB's address will be returned.

In kernel-mode debugging, this is the location of the KTHREAD structure, which is returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff545889">GetCurrentThreadAddr</a>.  If <i>CurrentThread</i> is <b>NULL</b>, the PEB for the current process is returned.

In user-mode debugging, <i>CurrentThread</i> is ignored.

`Address`

Receives the address of the PEB for the current operating system process or, in kernel-mode debugging, when <i>CurrentThread</i> is not <b>NULL</b>, for the system process that contains the thread that is specified by <i>CurrentThread</i>.


## Return Value

None

## Remarks

In user-mode debugging, the PEB for the current thread is returned.

In kernel-mode debugging, if <i>CurrentThread</i> is <b>NULL</b>, the PEB for the operating system process in which the last event occurred is returned.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545889">GetCurrentThreadAddr</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549267">GetTebAddress</a>