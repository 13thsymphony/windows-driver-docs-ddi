---
UID : NF:engextcpp.ExtRemoteTypedList.ExtRemoteTypedList
title : ExtRemoteTypedList::ExtRemoteTypedList method
author : windows-driver-content
description : The ExtRemoteTypedList class extends the ExtRemoteList class. The ExtRemoteTypedList class adds type information allowing each item in the list to be represented by an instance of the ExtRemoteTyped class.
old-location : debugger\extremotetypedlist.htm
old-project : debugger
ms.assetid : a7b87f06-491a-4b41-a355-0f2806c0dd8a
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ExtRemoteTypedList, ExtRemoteTypedList::ExtRemoteTypedList, ExtRemoteTypedList
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : engextcpp.hpp
req.include-header : Engextcpp.hpp
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : ExtRemoteTypedList
req.alt-loc : engextcpp.hpp
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
req.typenames : "*PSILO_DRIVER_CAPABILITIES, SILO_DRIVER_CAPABILITIES"
---


# ExtRemoteTypedList method
The <b>ExtRemoteTypedList</b> class extends the <a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a> class.  The <b>ExtRemoteTypedList</b> class adds type information allowing each item in the list to be represented by an instance of the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> class.

The <b>ExtRemoteTypedList</b> class includes the following constructors and methods:


<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>



<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>



<a href="https://msdn.microsoft.com/f6e2d8e3-294d-45d8-8fc6-33af3a746244">SetTypeAndLink</a>



<a href="https://msdn.microsoft.com/3bf50952-7ac9-4c6b-9318-dd64748de9d2">GetTypedNodePtr</a>



<a href="https://msdn.microsoft.com/f74090c9-4e15-4d6c-bb62-b8d5c56d5a1c">GetTypedNode</a>




The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <b>m_TypeId</b> is not zero, <i>Type</i> is not used.

The location in the target's memory of the base address of the module that contains the type specified by <b>m_TypeId</b>.  If <b>m_TypeId</b> is zero, <b>m_TypeModBase</b> is not used.

The type ID of the type relative to the module specified by <b>m_TypeModBase</b>.  If <b>m_TypeId</b> is zero, <b>m_Type</b> is used to specify the type of the list items.

## Syntax



## Parameters

`Head`



`Type`



`LinkField`



`TypeModBase`



`TypeId`



`CacheCookie`



`Double`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | engextcpp.hpp (include Engextcpp.hpp) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotelist.md">ExtRemoteList</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ExtRemoteData)</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList::ExtRemoteTypedList(ULONG64)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f74090c9-4e15-4d6c-bb62-b8d5c56d5a1c">GetTypedNode</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/3bf50952-7ac9-4c6b-9318-dd64748de9d2">GetTypedNodePtr</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/f6e2d8e3-294d-45d8-8fc6-33af3a746244">SetTypeAndLink</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTypedList class%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>