---
UID: NF:wdbgexts.ReadControlSpace64
title: ReadControlSpace64 function
author: windows-driver-content
description: The ReadControlSpace64 function reads the processor-specific control space into the array pointed to by buf.
old-location: debugger\readcontrolspace64.htm
old-project: debugger
ms.assetid: 4fa3d51a-d2f5-4b5f-abc0-515bf7211b87
ms.author: windowsdriverdev
ms.date: 1/19/2018
ms.keywords: wdbgexts/ReadControlSpace64, WdbgExts_Ref_3327dad4-903c-4285-b3cc-fe408d15f129.xml, debugger.readcontrolspace64, ReadControlSpace64 function [Windows Debugging], ReadControlSpace64
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdbgexts.h
req.include-header: Wdbgexts.h, Dbgeng.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdbgexts.h
apiname:
-	ReadControlSpace64
product: Windows
targetos: Windows
req.typenames: EXT_TDOP
req.product: Windows 10 or later.
---


# ReadControlSpace64 function
The <b>ReadControlSpace64</b> function reads the processor-specific control space into the array pointed to by <i>buf</i>.

## Syntax

````
__inline VOID ReadControlSpace64(
   USHORT  processor,
   ULONG64 address,
   PVOID   buf,
   ULONG   size
);
````

## Parameters

`processor`

Specifies the number of the processor whose control space is to be read.

`address`

Specifies the address of the control space.

`buf`

Specifies the address of an array of bytes to hold the control space data.

`size`

Specifies the number of bytes in the array pointed to by <i>buf</i>.


## Return Value

None

## Remarks

If you are writing 32-bit code, you should use <a href="..\wdbgexts\ns-wdbgexts-_readcontrolspace.md">ReadControlSpace</a> instead. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff537780">32-Bit Pointers and 64-Bit Pointers</a> for details.

If you are writing a WdbgExts extension, include <b>wdbgexts.h</b>. If you are writing a DbgEng extension that calls this function, include <b>wdbgexts.h</b> before <b>dbgeng.h</b> (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff561480">Writing DbgEng Extension Code</a> for details).


The <b>ReadTypedControlSpace32</b> macro is a thin wrapper around the <b>ReadControlSpace64</b> function.  It is provided as a convenience for reading processor-specific control space into a structure.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>void ReadTypedControlSpace32(
    _Proc,
    _Addr,
    _Buf
);</pre>
</td>
</tr>
</table></span></div>
<i>_Proc</i>

Specifies the number of the processor whose control space is to be read.

<i>_Addr</i>

Specifies the address of the control space.

<i>_Buf</i>

Specifies the object into which the control space data is read.

<b>Return value</b>

This macro does not return a value.



The parameters provided to this macro are the same as those provided to the <b>ReadControlSpace64</b> function except that instead of providing a pointer to a structure and its size, the structure can be provided directly.

The <b>ReadTypedControlSpace64</b> macro is a thin wrapper around the <b>ReadControlSpace64</b> function.  It is provided as a convenience for reading processor-specific control space into a structure.

<div class="code"><span codelanguage="ManagedCPlusPlus"><table>
<tr>
<th>C++</th>
</tr>
<tr>
<td>
<pre>void ReadTypedControlSpace64(
    _Proc,
    _Addr,
    _Buf
);</pre>
</td>
</tr>
</table></span></div>
<i>_Proc</i>

Specifies the number of the processor whose control space is to be read.

<i>_Addr</i>

Specifies the address of the control space.

<i>_Buf</i>

Specifies the object into which the control space data is read.

<b>Return value</b>

This macro does not return a value.



The parameters provided to this macro are the same as those provided to the <b>ReadControlSpace64</b> function except that instead of providing a pointer to a structure and its size, the structure can be provided directly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | wdbgexts.h (include Wdbgexts.h, Dbgeng.h) |
| **Library** | NtosKrnl.exe |