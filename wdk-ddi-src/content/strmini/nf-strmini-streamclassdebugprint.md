---
UID: NF.strmini.StreamClassDebugPrint
title: StreamClassDebugPrint function
author: windows-driver-content
description: In a checked build environment, the minidriver can use the StreamClassDebugPrint routine to print debug messages to the application window and to the Debugger Command window.
old-location: stream\streamclassdebugprint.htm
old-project: stream
ms.assetid: a8b7efd2-7773-44dc-92de-85b03c31ada8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: StreamClassDebugPrint
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
req.alt-api: StreamClassDebugPrint
req.alt-loc: Stream.lib,Stream.dll
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
req.product: Windows 10 or later.
---

# StreamClassDebugPrint function



## -description
In a checked build environment, the minidriver can use the <b>StreamClassDebugPrint</b> routine to print debug messages to the application window and to the Debugger Command window.


## -syntax

````
VOID __cdecl StreamClassDebugPrint(
  _In_ STREAM_DEBUG_LEVEL DebugPrintLevel,
  _In_ PCCHAR             DebugMessage,
       ...                arguments
);
````


## -parameters

### -param DebugPrintLevel [in]

Specifies an enumeration of type <a href="..\strmini\ne-strmini-stream_debug_level.md">STREAM_DEBUG_LEVEL</a>. The debugger prints messages if this parameter is less than or equal to the <i>StreamDebug</i> variable in <i>stream.sys</i> symbols.

### -param DebugMessage [in]

Points to a <b>NULL</b>-terminated string containing the message to print to the application window and to the Debugger Command window.

### -param arguments 

Specifies a variable argument list containing optional arguments for the format string, as in <b>printf</b>.

## -returns
None

## -remarks
For more information, see <a href="https://msdn.microsoft.com/544b922b-58e4-4cbb-a76c-d8e13ae17e55">Stream Class Debugging</a>.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Strmini.h (include Strmini.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Stream.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="devtest.dbgprint">DbgPrint</a>
</dt>
<dt>
<a href="stream.streamclassdebugassert">StreamClassDebugAssert</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20StreamClassDebugPrint routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
