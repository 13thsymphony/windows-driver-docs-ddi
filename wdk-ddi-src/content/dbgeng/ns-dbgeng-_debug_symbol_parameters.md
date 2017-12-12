---
UID: NS.DBGENG._DEBUG_SYMBOL_PARAMETERS
title: _DEBUG_SYMBOL_PARAMETERS
author: windows-driver-content
description: The DEBUG_SYMBOL_PARAMETERS structure describes a symbol in a symbol group.
old-location: debugger\debug_symbol_parameters.htm
old-project: debugger
ms.assetid: c73ea2b0-e87a-4fb1-9164-ff14d43f1426
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DEBUG_SYMBOL_PARAMETERS, DEBUG_SYMBOL_PARAMETERS, *PDEBUG_SYMBOL_PARAMETERS
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
req.alt-api: DEBUG_SYMBOL_PARAMETERS
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
---

# _DEBUG_SYMBOL_PARAMETERS structure



## -description
The <b>DEBUG_SYMBOL_PARAMETERS</b> structure describes a symbol in a symbol group.



## -syntax

````
typedef struct _DEBUG_SYMBOL_PARAMETERS {
  ULONG64 Module;
  ULONG   TypeId;
  ULONG   ParentSymbol;
  ULONG   SubElements;
  ULONG   Flags;
  ULONG64 Reserved;
} DEBUG_SYMBOL_PARAMETERS, *PDEBUG_SYMBOL_PARAMETERS;
````


## -struct-fields

### -field Module

The location in the target's virtual address space of the base of the module to which the symbol belongs.


### -field TypeId

The type ID of the symbol.


### -field ParentSymbol

The index within the symbol group of the symbol's parent symbol.  If the parent symbol is not known, <b>ParentSymbol</b> is DEBUG_ANY_ID.


### -field SubElements

The number of children of the symbol.  If this symbol has never been expanded within this symbol group, this number will be an estimate that is based on the symbol's type.


### -field Flags

The symbol flags.  See <a href="https://msdn.microsoft.com/library/windows/hardware/ff541692">DEBUG_SYMBOL_XXX</a> for details.


### -field Reserved

Set to zero.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>DbgEng.h (include DbgEng.h)</dt>
</dl>
</td>
</tr>
</table>