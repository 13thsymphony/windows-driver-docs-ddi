---
UID: NF:dbgeng.IDebugSymbols3.GetFieldOffsetWide
title: IDebugSymbols3::GetFieldOffsetWide method
author: windows-driver-content
description: The GetFieldOffsetWide method returns the offset of a field from the base address of an instance of a type.
old-location: debugger\getfieldoffsetwide.htm
old-project: debugger
ms.assetid: 4a9b90dd-72b2-4625-8b73-bc0dca6ba905
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetFieldOffsetWide, GetFieldOffsetWide
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
req.alt-api: IDebugSymbols3.GetFieldOffsetWide
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
req.typenames: *PDOT4_ACTIVITY, DOT4_ACTIVITY
---

# IDebugSymbols3::GetFieldOffsetWide method



## -description
The <b>GetFieldOffsetWide</b>  method returns the offset of a field from the base address of an instance of a type.



## -syntax

````
HRESULT GetFieldOffsetWide(
  [in]  ULONG64 Module,
  [in]  ULONG   TypeId,
  [in]  PCWSTR  Field,
  [out] PULONG  Offset
);
````


## -parameters

### -param Module [in]

Specifies the module containing the types of both the container and the field.


### -param TypeId [in]

Specifies the type ID of the type containing the field.


### -param Field [in]

Specifies the name of the field whose offset is requested.  Subfields may be specified by using a dot-separated path.


### -param Offset [out]

Receives the offset of the specified field from the base memory location of an instance of the type. 


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The field <i>Field</i> could not be found in the type specified by <i>TypeId</i>.

 


## -remarks
An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the location of this field relative to the location of MyStruct structure can be found by setting the <i>Field</i> parameter to "MyField.MySubField".

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.


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