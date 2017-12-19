---
UID: NF.engextcpp.ExtBuffer.Set
title: ExtBuffer::Set method
author: windows-driver-content
description: The Set method sets the typed data represented by the ExtRemoteTyped object.
old-location: debugger\extremotetyped_set_bool.htm
old-project: Debugger
ms.assetid: e75c17d2-fdf7-4dba-9892-74c764956924
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: ExtBuffer, ExtBuffer::Set, Set
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTyped.Set
req.alt-loc: engextcpp.hpp
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

# ExtBuffer::Set method



## -description
The <b>Set</b> method sets the typed data represented by the <a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a> object.



## -syntax

````
void Set(
  [in] bool    PtrTo,
  [in] ULONG64 TypeModBase,
  [in] ULONG   TypeId,
  [in] ULONG64 Offset
);
````


## -parameters

### -param PtrTo [in]

Specifies whether or not to set the <b>ExtRemoteTyped</b> instance to the specified typed data, or to a pointer to the specified typed data.  If <i>PtrTo</i> is <code>true</code>, the <b>ExtRemoteTyped</b> instance will be a pointer to the typed data.


### -param TypeModBase [in]

The base address of the module to which the type belongs.


### -param TypeId [in]

The type ID of the type.


### -param Offset [in]

Specifies the location of the data in the target's memory.


## -returns
This method does not return a value.


## -remarks


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
<dt>Engextcpp.hpp (include Engextcpp.hpp)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetyped.md">ExtRemoteTyped</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr">ExtRemoteTyped::Set (PCSTR)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr_ulong64">ExtRemoteTyped::Set (PCSTR, ULONG64)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_set_pcstr_ulong64_bool">ExtRemoteTyped::Set (PCSTR, ULONG64, bool)</a>
</dt>
<dt>
<a href="debugger.extremotetyped_setprint">ExtRemoteTyped::SetPrint</a>
</dt>
<dt>
<a href="..\engextcpp\nl-engextcpp-extremotetypedlist.md">ExtRemoteTypedList</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [Debugger\debugger]:%20ExtRemoteTyped.Set method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

