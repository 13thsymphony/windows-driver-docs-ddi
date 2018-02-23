---
UID: NF:dbgeng.IDebugSymbols3.GetFieldTypeAndOffsetWide
title: IDebugSymbols3::GetFieldTypeAndOffsetWide method
author: windows-driver-content
description: The GetFieldTypeAndOffsetWide method returns the type of a field and its offset within a container.
old-location: debugger\getfieldtypeandoffsetwide.htm
old-project: Debugger
ms.assetid: b4e38b33-2f23-4439-b0bc-ab3524e5180e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: debugger.getfieldtypeandoffsetwide, GetFieldTypeAndOffsetWide method [Windows Debugging], GetFieldTypeAndOffsetWide, IDebugSymbols3, GetFieldTypeAndOffsetWide method [Windows Debugging], IDebugSymbols3 interface, IDebugSymbols3::GetFieldTypeAndOffsetWide, dbgeng/IDebugSymbols3::GetFieldTypeAndOffsetWide, IDebugSymbols3 interface [Windows Debugging], GetFieldTypeAndOffsetWide method
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	dbgeng.h
apiname:
-	IDebugSymbols3.GetFieldTypeAndOffsetWide
product: Windows
targetos: Windows
req.typenames: DOT4_ACTIVITY, *PDOT4_ACTIVITY
---


# GetFieldTypeAndOffsetWide method
The <b>GetFieldTypeAndOffsetWide</b>  method returns the type of a field and its offset within a container.

## Syntax

````
HRESULT GetFieldTypeAndOffsetWide(
  [in]            ULONG64 Module,
  [in]            ULONG   ContainerTypeId,
  [in]            PCWSTR  Field,
  [out, optional] PULONG  FieldTypeId,
  [out, optional] PULONG  Offset
);
````

## Parameters

`Module`

Specifies the module containing the types of both the container and the field.

`ContainerTypeId`

Specifies the type ID for the container's type.  Examples of containers include structures, unions, and classes.

`Field`

Specifies the name of the field whose type and offset are requested.  Subfields may be specified by using a dot-separated path.

`FieldTypeId`

Receives the type ID of the field.

`Offset`

Receives the offset of the field <i>Field</i> from the base memory location of an instance of the container.


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
The field <i>Field</i> could not be found in the type specified by <i>ContainerTypeId</i>.

</td>
</tr>
</table>

## Remarks

An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the type of this field and its location relative to the location of MyStruct structure can be found by passing "MyField.MySubField" as the <i>Field</i> parameter to this method.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | dbgeng.h (include Dbgeng.h) |
| **Library** | dbgeng.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>



<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20IDebugSymbols3::GetFieldTypeAndOffsetWide method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>