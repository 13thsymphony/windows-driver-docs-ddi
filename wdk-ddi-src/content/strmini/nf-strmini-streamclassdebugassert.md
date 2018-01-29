---
UID : NF:strmini.StreamClassDebugAssert
title : StreamClassDebugAssert function
author : windows-driver-content
description : A minidriver can use the StreamClassDebugAssert routine in a checked build environment to fail an assert, causing the stream class driver to output a debug message and break into the kernel debugger.
old-location : stream\streamclassdebugassert.htm
old-project : stream
ms.assetid : df9b3231-4c43-4d4b-b128-e8d6a9f21b17
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : strclass-routines_6f9302e6-592f-4097-830c-83b05a54d335.xml, stream.streamclassdebugassert, strmini/StreamClassDebugAssert, StreamClassDebugAssert routine [Streaming Media Devices], StreamClassDebugAssert
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : strmini.h
req.include-header : Strmini.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Stream.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product : Windows 10 or later.
---


# StreamClassDebugAssert function
A minidriver can use the <b>StreamClassDebugAssert</b> routine in a checked build environment to fail an assert, causing the stream class driver to output a debug message and break into the kernel debugger.

## Syntax

````
VOID StreamClassDebugAssert(
  _In_ PCHAR File,
  _In_ ULONG Line,
  _In_ PCHAR AssertText,
  _In_ ULONG AssertValue
);
````

## Parameters

`File`

Pointer to a <b>NULL</b>-terminated string containing the file name in which the assert occurred.

`Line`

Specifies the line number of the assert.

`AssertText`

Pointer to a <b>NULL</b>-terminated string containing text to be printed in the debug message.

`AssertValue`

Specifies a value to be printed in the debug message.


## Return Value

None

## Remarks

When running a checked version of the class driver, asserts are recognized, and result in a debug message and breakpoint. When running a free version of the class driver, asserts are ignored. For more information, see <a href="https://msdn.microsoft.com/544b922b-58e4-4cbb-a76c-d8e13ae17e55">Stream Class Debugging</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | strmini.h (include Strmini.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\strmini\nf-strmini-streamclassdebugprint.md">StreamClassDebugPrint</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543626">DbgBreakPoint</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassDebugAssert routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>