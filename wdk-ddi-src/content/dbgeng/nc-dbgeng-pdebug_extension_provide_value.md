---
UID: NC:dbgeng.PDEBUG_EXTENSION_PROVIDE_VALUE
title: PDEBUG_EXTENSION_PROVIDE_VALUE
author: windows-driver-content
description: The DebugExtensionProvideValue callback function sets pseudo-register values.C++ CALLBACK* PDEBUG_EXTENSION_PROVIDE_VALUE DebugExtensionProvideValue;
old-location: debugger\debugextensionprovidevalue.htm
old-project: debugger
ms.assetid: b4b1953c-dc1b-495a-ab58-5cfaa6064b23
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
req.alt-api: DebugExtensionProvideValue
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

# PDEBUG_EXTENSION_PROVIDE_VALUE callback



## -description
The <b>DebugExtensionProvideValue</b> callback function sets <a href="https://msdn.microsoft.com/fa334c9f-46c6-4288-95ce-43128fff7f03">pseudo-register</a> values.



## -prototype

````
 CALLBACK* PDEBUG_EXTENSION_PROVIDE_VALUE DebugExtensionProvideValue;
````


## -parameters

### -param Client [in]

A client to use if the extension needs DbgEng functions.


### -param Flags [in]

Provides behavioral flags. This parameter is currently reserved.


### -param Name [in]

The name of the value to return. This name might be one of the names that the <a href="..\dbgeng\nc-dbgeng-pdebug_extension_query_value_names.md">DebugExtensionQueryValueNames</a> function returned or a name that the caller might already be aware of.


### -param Value [out]

A pointer to the value to be set.


### -param TypeModBase [out]

The base starting address for <i>Client.</i>


### -param TypeId [out]

A pointer to the ID for the type of <i>Value</i>.


### -param TypeFlags [out]

A parameter that you can use to return one of the following flags: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -param DEBUG_EXT_PVTYPE_IS_VALUE

</td>
<td width="60%">
The value that is pointed to by <i>Value</i> is not a pointer. 

</td>
</tr>
<tr>

### -param DEBUG_EXT_PVTYPE_IS_POINTER

</td>
<td width="60%">
The value that is pointed to by <i>Value</i> is an address for a pointer to data of the type that TypeModBase and TypeId specify.

</td>
</tr>
</table>
 


## -returns
<b>DebugExtensionProvideValue</b> might return one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The function was successfully completed.

 

This function might also return error values. For more information about possible return values, see <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a>.


## -remarks
The name that the <i>Name</i> parameter specifies must start with <b>$$</b> and have a terminating NULL character. 

<i>DebugExtensionProvideValue</i> is called <b>PDEBUG_EXTENSION_PROVIDE_VALUE</b> in the Dbgeng.h header file. 


## -see-also
<dl>
<dt>
<a href="..\dbgeng\nc-dbgeng-pdebug_extension_initialize.md">DebugExtensionInitialize</a>
</dt>
<dt><i>DebugExtensionNotify</i></dt>
<dt><i>DebugExtensionQueryValueNames</i></dt>
<dt><i>DebugExtensionUninitialize</i></dt>
<dt><i>KnownStructOutput</i></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20PDEBUG_EXTENSION_PROVIDE_VALUE callback function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

