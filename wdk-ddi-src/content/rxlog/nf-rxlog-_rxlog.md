---
UID: NF:rxlog._RxLog
title: "_RxLog function"
author: windows-driver-content
description: "_RxLog takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled."
old-location: ifsk\_rxlog.htm
old-project: ifsk
ms.assetid: 00f6c2d9-7521-46c8-b37e-2be304d8a045
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "_RxLog, _RxLog function [Installable File System Drivers], ifsk._rxlog, rxlog/_RxLog, rxref_2c140100-e24e-4fe0-935a-81fa6840db24.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxlog.h
req.include-header: Rxlog.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rxlog.h
api_name:
-	_RxLog
product:
- Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---


# _RxLog function
<b>_RxLog</b> takes a format string and variable number of parameters and formats an output string for recording as an I/O error log entry if logging is enabled.

## Syntax

```
void _RxLog(
  PCSTR format,
  ...   
);
```

## Parameters

`format`

TBD

`Arg1`




## Return Value

None

## Remarks

It is recommended that the <b>RxLog</b> macro be used instead of calling the <b>_RxLog</b> routine directly.

If logging is enabled, <b>_RxLog</b> will output a string for recording as an I/O error log entry based on the format string and number of variables passed.

The <b>_RxLog</b> routine supports the following format string descriptors:

%lN, %wN, %lS, %wS, %ld, %wd--a number

%x--a hexadecimal number

%c--a character

%s--an ASCII string

%Z--a Unicode string that contains ASCII characters

The <b>_RxLog</b> routine is limited to an output string of, at most, 48 lines, so the <i>Format</i> string cannot contain more than 48 '\n' characters. 

It is recommended that the <b>RxLog</b> macro be used to call this routine. On checked builds, the <b>RxLog</b> macro will call the <b>_RxLog</b> routine. On retail builds, the <b>RxLog</b> macro is defined to nothing.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | rxlog.h (include Rxlog.h) |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff554515">RxLogEventDirect</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554519">RxLogEventWithAnnotation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554524">RxLogEventWithBufferDirect</a>