---
UID: NC:dbgeng.PDEBUG_EXTENSION_QUERY_VALUE_NAMES
title: PDEBUG_EXTENSION_QUERY_VALUE_NAMES
author: windows-driver-content
description: The DebugExtensionQueryValueNames callback function recovers pseudo-register values.C++ CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;
old-location: debugger\debugextensionqueryvaluenames.htm
old-project: debugger
ms.assetid: cda46d60-913c-40f7-958a-5f9dea93bd0f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _DOT4_ACTIVITY, DOT4_ACTIVITY, *PDOT4_ACTIVITY
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
req.alt-api: DebugExtensionQueryValueNames
req.alt-loc: Dbgeng.h
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
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---

# PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback



## -description
The <b>DebugExtensionQueryValueNames</b> callback function recovers <a href="https://msdn.microsoft.com/fa334c9f-46c6-4288-95ce-43128fff7f03">pseudo-register</a> values.



## -prototype

````
 CALLBACK* PDEBUG_EXTENSION_QUERY_VALUE_NAMES DebugExtensionQueryValueNames;
````


## -parameters

### -param Client [in]

A client to use if the extension needs DbgEng functions.


### -param Flags [in]

Provides behavioral flags. This parameter is currently reserved.


### -param Buffer [out]

A string buffer that the caller provides, to be filled with the set of value names that the client wants to expose.


### -param BufferChars [in]

The count of wide characters in <i>Buffer</i>.


### -param BufferNeeded [out]

The number of wide characters that this function needs to complete successfully.


## -returns
<b>DebugExtensionQueryValueNames</b> might return one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The function was successfully completed.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The function completed without error, but it obtained only partial results.

 

This function might also return error values.  For more information about possible return values, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
Value names must start with <b>$$</b> and have a terminating NULL character. The <i>Buffer</i> string must also be NULL-terminated. For example, <i>Buffer</i> could be "$$myval1\0$$myval2\0\0".

<i>DebugExtensionQueryValueNames</i> is called <b>PDEBUG_EXTENSION_QUERY_VALUE_NAMES</b> in the Dbgeng.h header file.


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nc-dbgeng-pdebug_extension_initialize.md">DebugExtensionInitialize</a>
</dt>
<dt><i>DebugExtensionNotify</i></dt>
<dt><i>DebugExtensionProvideValue</i></dt>
<dt><i>DebugExtensionUninitialize</i></dt>
<dt><i>KnownStructOutput</i></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_QUERY_VALUE_NAMES callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

