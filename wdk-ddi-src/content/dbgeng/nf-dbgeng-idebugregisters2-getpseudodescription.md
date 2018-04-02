---
UID: NF:dbgeng.IDebugRegisters2.GetPseudoDescription
title: IDebugRegisters2::GetPseudoDescription method
author: windows-driver-content
description: The GetPseudoDescription method returns a description of a pseudo-register, including its name and type.
old-location: debugger\getpseudodescription.htm
old-project: debugger
ms.assetid: dc1c7b8a-1233-4f22-8c5f-273f370a1e06
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: GetPseudoDescription method [Windows Debugging], GetPseudoDescription method [Windows Debugging], IDebugRegisters2 interface, GetPseudoDescription,IDebugRegisters2.GetPseudoDescription, IDebugRegisters2, IDebugRegisters2 interface [Windows Debugging], GetPseudoDescription method, IDebugRegisters2::GetPseudoDescription, IDebugRegisters_7b1f8069-32d0-4fb4-9cee-7fd045bae8d3.xml, dbgeng/IDebugRegisters2::GetPseudoDescription, debugger.getpseudodescription
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: DbgEng.h
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
-	COM
api_location:
-	dbgeng.h
api_name:
-	IDebugRegisters2.GetPseudoDescription
product:
- Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# IDebugRegisters2::GetPseudoDescription method
The <b>GetPseudoDescription</b>  method returns a description of a pseudo-register, including its name and type.

## Syntax

```
HRESULT GetPseudoDescription(
  ULONG    Register,
  PSTR     NameBuffer,
  ULONG    NameBufferSize,
  PULONG   NameSize,
  PULONG64 TypeModule,
  PULONG   TypeId
);
```

## Parameters

`Register`

Specifies the index of the pseudo-register whose description is requested.  The index is always between zero and the number of pseudo-registers (returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff547957">GetNumberPseudoRegisters</a>) minus one.

`NameBuffer`

Receives the name of the pseudo-register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

`NameBufferSize`

Specifies the size, in characters, of the buffer that <i>NameBuffer </i>specifies.

`NameSize`

Receives the size in characters of the name of the pseudo-register.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

`TypeModule`

Receives the base address of the module to which the register's type belongs.  If the type of the register is not known, zero is returned.  If <i>TypeModule</i> is <b>NULL</b>, no information is returned.

`TypeId`

Receives the type ID of the type within the module returned in <i>TypeModule</i>.  If the type ID is not known, zero is returned.  If <i>TypeId</i> is <b>NULL</b>, no information is returned.


## Return Value

This list does not contain all the errors that might occur.  For a list of possible errors, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff549771">HRESULT Values</a>.

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
The method was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The description for the register was not available

</td>
</tr>
</table>

## Remarks

Descriptions are not always available for all registers.  If a pseudo-register does not have a value - for example, <b>$eventip</b> will not have a value before an event has occurred - or a type cannot be determined for a pseudo-register, this method will return E_FAIL.

For an overview of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff550825">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include DbgEng.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547957">GetNumberPseudoRegisters</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548206">GetPseudoIndexByName</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550835">IDebugRegisters2</a>