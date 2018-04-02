---
UID: NF:strmini.StreamClassDebugPrint
title: StreamClassDebugPrint function
author: windows-driver-content
description: In a checked build environment, the minidriver can use the StreamClassDebugPrint routine to print debug messages to the application window and to the Debugger Command window.
old-location: stream\streamclassdebugprint.htm
old-project: stream
ms.assetid: a8b7efd2-7773-44dc-92de-85b03c31ada8
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: StreamClassDebugPrint, StreamClassDebugPrint routine [Streaming Media Devices], strclass-routines_858a2dd4-ee74-44de-9293-05bd804c315d.xml, stream.streamclassdebugprint, strmini/StreamClassDebugPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Stream.lib
-	Stream.dll
api_name:
-	StreamClassDebugPrint
product:
- Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---


# StreamClassDebugPrint function
In a checked build environment, the minidriver can use the <b>StreamClassDebugPrint</b> routine to print debug messages to the application window and to the Debugger Command window.

## Syntax

```
void StreamClassDebugPrint(
  STREAM_DEBUG_LEVEL DebugPrintLevel,
  PCSTR              DebugMessage,
  ...                
);
```

## Parameters

`DebugPrintLevel`

Specifies an enumeration of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff568302">STREAM_DEBUG_LEVEL</a>. The debugger prints messages if this parameter is less than or equal to the <i>StreamDebug</i> variable in <i>stream.sys</i> symbols.

`DebugMessage`

Points to a <b>NULL</b>-terminated string containing the message to print to the application window and to the Debugger Command window.

`Arg1`




## Return Value

None

## Remarks

For more information, see <a href="https://msdn.microsoft.com/544b922b-58e4-4cbb-a76c-d8e13ae17e55">Stream Class Debugging</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | strmini.h (include Strmini.h) |
| **Library** | Stream.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543632">DbgPrint</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568233">StreamClassDebugAssert</a>