---
UID: NF:dbgeng.IDebugSymbols3.GetFieldOffsetWide
title: IDebugSymbols3::GetFieldOffsetWide method
author: windows-driver-content
description: The GetFieldOffsetWide method returns the offset of a field from the base address of an instance of a type.
old-location: debugger\getfieldoffsetwide.htm
old-project: debugger
ms.assetid: 4a9b90dd-72b2-4625-8b73-bc0dca6ba905
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: GetFieldOffsetWide method [Windows Debugging], GetFieldOffsetWide method [Windows Debugging], IDebugSymbols3 interface, GetFieldOffsetWide,IDebugSymbols3.GetFieldOffsetWide, IDebugSymbols3, IDebugSymbols3 interface [Windows Debugging], GetFieldOffsetWide method, IDebugSymbols3::GetFieldOffsetWide, dbgeng/IDebugSymbols3::GetFieldOffsetWide, debugger.getfieldoffsetwide
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
-	IDebugSymbols3.GetFieldOffsetWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetFieldOffsetWide method
The <b>GetFieldOffsetWide</b>  method returns the offset of a field from the base address of an instance of a type.

## Syntax

````
HRESULT GetFieldOffsetWide(
  [in]  ULONG64 Module,
  [in]  ULONG   TypeId,
  [in]  PCWSTR  Field,
  [out] PULONG  Offset
);
````

## Parameters

`Module`

Specifies the module containing the types of both the container and the field.

`TypeId`

Specifies the type ID of the type containing the field.

`Field`

Specifies the name of the field whose offset is requested.  Subfields may be specified by using a dot-separated path.

`Offset`

Receives the offset of the specified field from the base memory location of an instance of the type.


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
<dt><b>E_NOINTERFACE</b></dt>
</dl>
</td>
<td width="60%">
The field <i>Field</i> could not be found in the type specified by <i>TypeId</i>.

</td>
</tr>
</table>

## Remarks

An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the location of this field relative to the location of MyStruct structure can be found by setting the <i>Field</i> parameter to "MyField.MySubField".

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |