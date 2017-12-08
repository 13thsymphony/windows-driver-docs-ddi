---
UID: NS.dbgeng._DEBUG_GET_TEXT_COMPLETIONS_IN
title: DEBUG_GET_TEXT_COMPLETIONS_IN
author: windows-driver-content
description: Defines information about text completions to get.
old-location: debugger\debug_get_text_completions_in.htm
old-project: debugger
ms.assetid: 1B8B0B7D-346D-41FC-B718-60B04F10702C
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: DEBUG_GET_TEXT_COMPLETIONS_IN, DEBUG_GET_TEXT_COMPLETIONS_IN, *PDEBUG_GET_TEXT_COMPLETIONS_IN
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
req.alt-api: DEBUG_GET_TEXT_COMPLETIONS_IN
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

# DEBUG_GET_TEXT_COMPLETIONS_IN structure



## -description
<p>Defines information about text completions to get. </p>


## -syntax

````
typedef struct _DEBUG_GET_TEXT_COMPLETIONS_IN {
  ULONG   Flags;
  ULONG   MatchCountLimit;
  ULONG64 Reserved[3];
} DEBUG_GET_TEXT_COMPLETIONS_IN, *PDEBUG_GET_TEXT_COMPLETIONS_IN;
````


## -struct-fields
<dl>

### -field Flags

<dd>
<p>Flags. Valid flag values include the following:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_DOT_COMMANDS"></a><a id="debug_get_text_completions_no_dot_commands"></a><dl>

### -field DEBUG_GET_TEXT_COMPLETIONS_NO_DOT_COMMANDS


### -field 0x00000001

</dl>
</td>
<td width="60%">
<p>Do not include dot commands. Dot commands begin with a period (.).</p>
</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_EXTENSION_COMMANDS"></a><a id="debug_get_text_completions_no_extension_commands"></a><dl>

### -field DEBUG_GET_TEXT_COMPLETIONS_NO_EXTENSION_COMMANDS


### -field 0x00000002

</dl>
</td>
<td width="60%">
<p>Do not include extension commands. </p>
</td>
</tr>
<tr>
<td width="40%"><a id="DEBUG_GET_TEXT_COMPLETIONS_NO_SYMBOLS"></a><a id="debug_get_text_completions_no_symbols"></a><dl>

### -field DEBUG_GET_TEXT_COMPLETIONS_NO_SYMBOLS


### -field 0x00000004

</dl>
</td>
<td width="60%">
<p>Do not include completions with symbols.</p>
</td>
</tr>
</table>
<p> </p>
</dd>

### -field MatchCountLimit

<dd>
<p>The limit of matches.</p>
</dd>

### -field Reserved

<dd>
<p>Reserved. </p>
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