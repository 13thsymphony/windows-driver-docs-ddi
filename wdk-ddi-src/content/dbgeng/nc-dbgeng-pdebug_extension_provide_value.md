---
UID: NC:dbgeng.PDEBUG_EXTENSION_PROVIDE_VALUE
title: PDEBUG_EXTENSION_PROVIDE_VALUE
author: windows-driver-content
description: The DebugExtensionProvideValue callback function sets pseudo-register values.C++ CALLBACK* PDEBUG_EXTENSION_PROVIDE_VALUE DebugExtensionProvideValue;
old-location: debugger\debugextensionprovidevalue.htm
old-project: debugger
ms.assetid: b4b1953c-dc1b-495a-ab58-5cfaa6064b23
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: DEBUG_EXT_PVTYPE_IS_POINTER, DEBUG_EXT_PVTYPE_IS_VALUE, DebugExtensionProvideValue, DebugExtensionProvideValue callback function [Windows Debugging], Extensions_Ref_fa822b69-6941-46e9-8b68-d57dd8d19d14.xml, PDEBUG_EXTENSION_PROVIDE_VALUE, dbgeng/DebugExtensionProvideValue, debugger.debugextensionprovidevalue
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
-	DebugExtensionProvideValue
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# PDEBUG_EXTENSION_PROVIDE_VALUE callback function
The <b>DebugExtensionProvideValue</b> callback function sets <a href="https://msdn.microsoft.com/fa334c9f-46c6-4288-95ce-43128fff7f03">pseudo-register</a> values.
<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre> CALLBACK* PDEBUG_EXTENSION_PROVIDE_VALUE DebugExtensionProvideValue;</pre>
</td>
</tr>
</table></span></div>

## Syntax

```
PDEBUG_EXTENSION_PROVIDE_VALUE PdebugExtensionProvideValue;

HRESULT PdebugExtensionProvideValue(
  PDEBUG_CLIENT Client,
  ULONG Flags,
  PCWSTR Name,
  PULONG64 Value,
  PULONG64 TypeModBase,
  PULONG TypeId,
  PULONG TypeFlags
)
{...}
```

## Parameters

`Client`

A client to use if the extension needs DbgEng functions.

`Flags`

Provides behavioral flags. This parameter is currently reserved.

`Name`

The name of the value to return. This name might be one of the names that the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540490">DebugExtensionQueryValueNames</a> function returned or a name that the caller might already be aware of.

`Value`

A pointer to the value to be set.

`TypeModBase`

The base starting address for <i>Client.</i>

`TypeId`

A pointer to the ID for the type of <i>Value</i>.

`TypeFlags`

A parameter that you can use to return one of the following flags: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEBUG_EXT_PVTYPE_IS_VALUE"></a><a id="debug_ext_pvtype_is_value"></a><dl>
<dt><b>DEBUG_EXT_PVTYPE_IS_VALUE</b></dt>
</dl>
</td>
<td width="60%">
The value that is pointed to by <i>Value</i> is not a pointer. 

</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_EXT_PVTYPE_IS_POINTER"></a><a id="debug_ext_pvtype_is_pointer"></a><dl>
<dt><b>DEBUG_EXT_PVTYPE_IS_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The value that is pointed to by <i>Value</i> is an address for a pointer to data of the type that TypeModBase and TypeId specify.

</td>
</tr>
</table>


## Return Value

<b>DebugExtensionProvideValue</b> might return one of the following values:

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
</table>
 

This function might also return error values. For more information about possible return values, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.

## Remarks

The name that the <i>Name</i> parameter specifies must start with <b>$$</b> and have a terminating NULL character. 

<i>DebugExtensionProvideValue</i> is called <b>PDEBUG_EXTENSION_PROVIDE_VALUE</b> in the Dbgeng.h header file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540476">DebugExtensionInitialize</a>



<i>DebugExtensionNotify</i>



<i>DebugExtensionQueryValueNames</i>



<i>DebugExtensionUninitialize</i>



<i>KnownStructOutput</i>