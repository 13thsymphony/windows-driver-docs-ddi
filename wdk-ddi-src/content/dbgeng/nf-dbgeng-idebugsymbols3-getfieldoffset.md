---
UID : NF:dbgeng.IDebugSymbols3.GetFieldOffset
title : IDebugSymbols3::GetFieldOffset method
author : windows-driver-content
description : The GetFieldOffset method returns the offset of a field from the base address of an instance of a type.
old-location : debugger\getfieldoffset2.htm
old-project : debugger
ms.assetid : 4081ddf9-673d-4df6-8698-726a70d32c03
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : IDebugSymbols3, IDebugSymbols3::GetFieldOffset, GetFieldOffset
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : dbgeng.h
req.include-header : Dbgeng.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IDebugSymbols.GetFieldOffset,IDebugSymbols2.GetFieldOffset,IDebugSymbols3.GetFieldOffset
req.alt-loc : dbgeng.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*PDOT4_ACTIVITY, DOT4_ACTIVITY"
---


# GetFieldOffset method
The <b>GetFieldOffset</b>  method returns the offset of a field from the base address of an instance of a type.

## Syntax

````
HRESULT GetFieldOffset(
  [in]  ULONG64 Module,
  [in]  ULONG   TypeId,
  [in]  PCSTR   Field,
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
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The field <i>Field</i> could not be found in the type specified by <i>TypeId</i>.

## Remarks

An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the location of this field relative to the location of MyStruct structure can be found by setting the <i>Field</i> parameter to "MyField.MySubField".

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |