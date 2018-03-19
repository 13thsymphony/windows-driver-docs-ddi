---
UID: NC:dbgeng.PDEBUG_EXTENSION_QUERY_VALUE_NAMES
title: PDEBUG_EXTENSION_QUERY_VALUE_NAMES
author: windows-driver-content
description: The DebugExtensionQueryValueNames callback function recovers pseudo-register values.C++ CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;
old-location: debugger\debugextensionqueryvaluenames.htm
old-project: debugger
ms.assetid: cda46d60-913c-40f7-958a-5f9dea93bd0f
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: DebugExtensionQueryValueNames, DebugExtensionQueryValueNames callback function [Windows Debugging], Extensions_Ref_d06137e2-2d0a-4760-b5f6-2f03355f8c07.xml, PDEBUG_EXTENSION_QUERY_VALUE_NAMES, dbgeng/DebugExtensionQueryValueNames, debugger.debugextensionqueryvaluenames
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dbgeng.h
req.include-header: 
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
-	UserDefined
api_location:
-	Dbgeng.h
api_name:
-	DebugExtensionQueryValueNames
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback function
The <b>DebugExtensionQueryValueNames</b> callback function recovers <a href="https://msdn.microsoft.com/fa334c9f-46c6-4288-95ce-43128fff7f03">pseudo-register</a> values.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;</pre>
</td>
</tr>
</table></span></div>

## Syntax

```
PDEBUG_EXTENSION_QUERY_VALUE_NAMES PdebugExtensionQueryValueNames;

HRESULT PdebugExtensionQueryValueNames(
  PDEBUG_CLIENT Client,
  ULONG Flags,
  PWSTR Buffer,
  ULONG BufferChars,
  PULONG BufferNeeded
)
{...}
```

## Parameters

`Client`

A client to use if the extension needs DbgEng functions.

`Flags`

Provides behavioral flags. This parameter is currently reserved.

`Buffer`

A string buffer that the caller provides, to be filled with the set of value names that the client wants to expose.

`BufferChars`

The count of wide characters in <i>Buffer</i>.

`BufferNeeded`

The number of wide characters that this function needs to complete successfully.


## Return Value

<b>DebugExtensionQueryValueNames</b> might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The function was successfully completed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The function completed without error, but it obtained only partial results.

</td>
</tr>
</table>
 

This function might also return error values.  For more information about possible return values, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

Value names must start with <b>$$</b> and have a terminating NULL character. The <i>Buffer</i> string must also be NULL-terminated. For example, <i>Buffer</i> could be "$$myval1\0$$myval2\0\0".

<i>DebugExtensionQueryValueNames</i> is called <b>PDEBUG_EXTENSION_QUERY_VALUE_NAMES</b> in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |

## See Also

<i>DebugExtensionNotify</i>



<a href="..\dbgeng\nc-dbgeng-pdebug_extension_initialize.md">DebugExtensionInitialize</a>



<i>DebugExtensionUninitialize</i>



<i>KnownStructOutput</i>



<i>DebugExtensionProvideValue</i>