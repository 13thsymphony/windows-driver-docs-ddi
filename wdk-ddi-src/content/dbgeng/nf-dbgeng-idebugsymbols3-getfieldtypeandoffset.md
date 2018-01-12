---
UID: NF:dbgeng.IDebugSymbols3.GetFieldTypeAndOffset
title: IDebugSymbols3::GetFieldTypeAndOffset method
author: windows-driver-content
description: The GetFieldTypeAndOffset method returns the type of a field and its offset within a container.
old-location: debugger\getfieldtypeandoffset.htm
old-project: debugger
ms.assetid: a73a3bb5-f9f4-41d7-9df7-c7f36a01d157
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: IDebugSymbols3, IDebugSymbols3::GetFieldTypeAndOffset, GetFieldTypeAndOffset
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
req.alt-api: IDebugSymbols3.GetFieldTypeAndOffset
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

# IDebugSymbols3::GetFieldTypeAndOffset method



## -description
The <b>GetFieldTypeAndOffset</b>  method returns the type of a field and its offset within a container.



## -syntax

````
HRESULT GetFieldTypeAndOffset(
  [in]            ULONG64 Module,
  [in]            ULONG   ContainerTypeId,
  [in]            PCSTR   Field,
  [out, optional] PULONG  FieldTypeId,
  [out, optional] PULONG  Offset
);
````


## -parameters

### -param Module [in]

Specifies the module containing the types of both the container and the field.


### -param ContainerTypeId [in]

Specifies the type ID for the container's type.  Examples of containers include structures, unions, and classes.


### -param Field [in]

Specifies the name of the field whose type and offset are requested.  Subfields may be specified by using a dot-separated path.


### -param FieldTypeId [out, optional]

Receives the type ID of the field.


### -param Offset [out, optional]

Receives the offset of the field <i>Field</i> from the base memory location of an instance of the container.


## -returns
This method may also return error values.  See <a href="https://msdn.microsoft.com/713f3ee2-2f5b-415e-9908-90f5ae428b43">Return Values</a> for more details.
<dl>
<dt><b>S_OK</b></dt>
</dl>The method was successful.
<dl>
<dt><b>E_NOINTERFACE</b></dt>
</dl>The field <i>Field</i> could not be found in the type specified by <i>ContainerTypeId</i>.

 


## -remarks
An example of a dot-separated path for the <i>Field</i> parameter is as follows.  Suppose the MyStruct structure contains a field <b>MyField</b> of type MySubStruct, and the MySubStruct structure contains the field <b>MySubField</b>.  Then the type of this field and its location relative to the location of MyStruct structure can be found by passing "MyField.MySubField" as the <i>Field</i> parameter to this method.

For more information about types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558931">Types</a>.  For more information about symbols, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558824">Symbols</a>.


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

## -see-also
<dl>
<dt>
<a href="..\dbgeng\nn-dbgeng-idebugsymbols3.md">IDebugSymbols3</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546758">GetFieldOffset</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549376">GetTypeId</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20IDebugSymbols3::GetFieldTypeAndOffset method%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

