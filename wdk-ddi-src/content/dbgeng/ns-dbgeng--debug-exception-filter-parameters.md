---
UID: NS.dbgeng._DEBUG_EXCEPTION_FILTER_PARAMETERS
title: DEBUG_EXCEPTION_FILTER_PARAMETERS
author: windows-driver-content
description: The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.
old-location: debugger\debug_exception_filter_parameters.htm
old-project: debugger
ms.assetid: 26a101c5-0866-44e3-948b-8d3ca4dd9d00
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: DEBUG_EXCEPTION_FILTER_PARAMETERS, DEBUG_EXCEPTION_FILTER_PARAMETERS, *PDEBUG_EXCEPTION_FILTER_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dbgeng.h
req.include-header: DbgEng.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DEBUG_EXCEPTION_FILTER_PARAMETERS
req.alt-loc: DbgEng.h
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
req.iface: IDebugSystemObjects4
---

# DEBUG_EXCEPTION_FILTER_PARAMETERS structure



## -description
<p>The DEBUG_EXCEPTION_FILTER_PARAMETERS structure contains the parameters for an exception filter.</p>


## -syntax

````
typedef struct _DEBUG_EXCEPTION_FILTER_PARAMETERS {
  ULONG ExecutionOption;
  ULONG ContinueOption;
  ULONG TextSize;
  ULONG CommandSize;
  ULONG SecondCommandSize;
  ULONG ExceptionCode;
} DEBUG_EXCEPTION_FILTER_PARAMETERS, *PDEBUG_EXCEPTION_FILTER_PARAMETERS;
````


## -struct-fields
<dl>

### -field <b>ExecutionOption</b>

<dd>
<p>The <a href="debug_filter_xxx.htm#break_status">break status</a> of the exception filter, including the terminator.  For possible values, see <b>DEBUG_FILTER_XXX</b>.</p>
</dd>

### -field <b>ContinueOption</b>

<dd>
<p>The <a href="debug_filter_xxx.htm#handling_status">handling status</a> of the exception filter.  For possible values, see <b>DEBUG_FILTER_XXX</b>.</p>
</dd>

### -field <b>TextSize</b>

<dd>
<p>The size, in characters, of the name (including the terminator) of the exception filter.  If the filter is an arbitrary exception filter, it does not have a name and <b>TextSize</b> is zero.</p>
</dd>

### -field <b>CommandSize</b>

<dd>
<p>The size, in characters, of the command (including the terminator) to execute upon the first chance of the exception.</p>
</dd>

### -field <b>SecondCommandSize</b>

<dd>
<p>The size, in characters, of the command (including the terminator) to execute upon the second chance of the exception.</p>
</dd>

### -field <b>ExceptionCode</b>

<dd>
<p>The exception code for the exception filter.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="debugger.getexceptionfilterparameters">GetExceptionFilterParameters</a>
</dt>
<dt>
<a href="debugger.setexceptionfilterparameters">SetExceptionFilterParameters</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20DEBUG_EXCEPTION_FILTER_PARAMETERS structure%20 RELEASE:%20(11/27/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
