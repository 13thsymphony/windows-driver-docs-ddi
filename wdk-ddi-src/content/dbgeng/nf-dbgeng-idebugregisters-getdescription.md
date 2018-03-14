---
UID: NF:dbgeng.IDebugRegisters.GetDescription
title: IDebugRegisters::GetDescription method
author: windows-driver-content
description: The GetDescription method returns the description of a register.
old-location: debugger\getdescription.htm
old-project: debugger
ms.assetid: 895d18e7-673e-41bb-a3be-eb5b4a778880
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetDescription method [Windows Debugging], GetDescription method [Windows Debugging], IDebugRegisters interface, GetDescription method [Windows Debugging], IDebugRegisters2 interface, GetDescription,IDebugRegisters.GetDescription, IDebugRegisters, IDebugRegisters interface [Windows Debugging], GetDescription method, IDebugRegisters2 interface [Windows Debugging], GetDescription method, IDebugRegisters2::GetDescription, IDebugRegisters::GetDescription, IDebugRegisters_aa062ab9-e090-4cad-b875-b6e99a019c16.xml, dbgeng/IDebugRegisters2::GetDescription, dbgeng/IDebugRegisters::GetDescription, debugger.getdescription
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
-	IDebugRegisters.GetDescription
-	IDebugRegisters2.GetDescription
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetDescription method
The <b>GetDescription</b>  method returns the description of a register.

## Syntax

````
HRESULT GetDescription(
  [in]            ULONG                       Register,
  [out, optional] PSTR                        NameBuffer,
  [in]            ULONG                       NameBufferSize,
  [out, optional] PULONG                      NameSize,
  [out, optional] PDEBUG_REGISTER_DESCRIPTION Desc
);
````

## Parameters

`Register`

Specifies the index of the register for which the description is requested.

`NameBuffer`

Specifies the buffer in which to store the name of the register.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

`NameBufferSize`

Specifies the size, in characters, of the buffer that  <i>NameBuffer</i> specifies.

`NameSize`

Receives the size, in characters, of the register's name in <i>NameBuffer</i> buffer.  If <i>NameSize</i> is <b>NULL</b>, this information is not returned.

`Desc`

Receives the description of the register.  See <a href="..\dbgeng\ns-dbgeng-_debug_register_description.md">DEBUG_REGISTER_DESCRIPTION</a> for more details.


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
<dt><b>S_FALSE</b></dt>
</dl>
</td>
<td width="60%">
The method was successful. However, the buffer was not large enough to hold the register's name, so it was truncated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_UNEXPECTED</b></dt>
</dl>
</td>
<td width="60%">
No target machine has been specified, or a description of the register could not be found.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
The index of the register requested is greater than the total number of registers on the target's machine.

</td>
</tr>
</table>

## Remarks

For an overview of the <a href="..\dbgeng\nn-dbgeng-idebugregisters.md">IDebugRegisters</a> interface and other register-related methods, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554369">Registers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include DbgEng.h) |