---
UID: NF:dbgeng.IDebugSymbols3.GetConstantNameWide
title: IDebugSymbols3::GetConstantNameWide method
author: windows-driver-content
description: The GetConstantNameWide method returns the name of the specified constant.
old-location: debugger\getconstantnamewide.htm
old-project: debugger
ms.assetid: 743d2f83-905b-4bc9-8e23-b330c3ca7629
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetConstantNameWide method [Windows Debugging], GetConstantNameWide method [Windows Debugging], IDebugSymbols3 interface, GetConstantNameWide,IDebugSymbols3.GetConstantNameWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetConstantNameWide method, IDebugSymbols3::GetConstantNameWide, dbgeng/IDebugSymbols3::GetConstantNameWide, debugger.getconstantnamewide
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: dbgeng.h
req.include-header: Dbgeng.h
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
req.lib: dbgeng.h
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
-	IDebugSymbols3.GetConstantNameWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetConstantNameWide method
The <b>GetConstantNameWide</b>  method returns the name of the specified constant.

## Syntax

````
HRESULT GetConstantNameWide(
  [in]            ULONG64 Module,
  [in]            ULONG   TypeId,
  [in]            ULONG64 Value,
  [out, optional] PWSTR   NameBuffer,
  [in]            ULONG   NameBufferSize,
  [out, optional] PULONG  NameSize
);
````

## Parameters

`Module`

Specifies the base address of the module in which the constant was defined.

`TypeId`

Specifies the type ID of the constant.

`Value`

Specifies the value of the constant.

`NameBuffer`

Receives the constant's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.

`NameBufferSize`

Specifies the size in characters of the buffer <i>NameBuffer</i>.

`NameSize`

Receives the size in characters of the constant's name.


## Return Value

This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.

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
The method was successful. However, the buffer was not large enough for the constant's name and it was truncated.

</td>
</tr>
</table>

## Remarks

For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |