---
UID: NF.dbgeng.IDebugSymbols3.GetConstantNameWide
title: IDebugSymbols3::GetConstantNameWide method
author: windows-driver-content
description: The GetConstantNameWide method returns the name of the specified constant.
old-location: debugger\getconstantnamewide.htm
old-project: Debugger
ms.assetid: 743d2f83-905b-4bc9-8e23-b330c3ca7629
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetConstantNameWide, GetConstantNameWide
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
req.alt-api: IDebugSymbols3.GetConstantNameWide
req.alt-loc: dbgeng.h
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

# IDebugSymbols3::GetConstantNameWide method



## -description
The <b>GetConstantNameWide</b>  method returns the name of the specified constant.



## -syntax

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


## -parameters

### -param Module [in]

Specifies the base address of the module in which the constant was defined.


### -param TypeId [in]

Specifies the type ID of the constant.


### -param Value [in]

Specifies the value of the constant.


### -param NameBuffer [out, optional]

Receives the constant's name.  If <i>NameBuffer</i> is <b>NULL</b>, this information is not returned.


### -param NameBufferSize [in]

Specifies the size in characters of the buffer <i>NameBuffer</i>.


### -param NameSize [out, optional]

Receives the size in characters of the constant's name.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>S_FALSE</b></dt>
</dl>The method was successful. However, the buffer was not large enough for the constant's name and it was truncated.

 


## -remarks
For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dbgeng.h (include Dbgeng.h)</dt>
</dl>
</td>
</tr>
</table>