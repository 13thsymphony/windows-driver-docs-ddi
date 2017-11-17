---
UID: NF.engextcpp.ExtRemoteTypedList.SetTypeAndLink
title: ExtRemoteTypedList::SetTypeAndLink
author: windows-driver-content
description: The SetTypeAndLink method sets the type information for the typed list.
old-location: debugger\extremotetypedlist_settypeandlink.htm
ms.assetid: f6e2d8e3-294d-45d8-8fc6-33af3a746244
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: debugger
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExtRemoteTypedList.SetTypeAndLink
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
ms.keywords: ExtRemoteTypedList, SetTypeAndLink, ExtRemoteTypedList::SetTypeAndLink
req.iface: ExtRemoteTypedList
---

# ExtRemoteTypedList::SetTypeAndLink method



## -description
<p>The <b>SetTypeAndLink</b> method sets the type information for the typed list.</p>


## -syntax

````
void SetTypeAndLink(
  [in]                PCSTR    Type,
  [in]                PCSTR    LinkField,
  [in]                ULONG64  TypeModBase,
  [in]                ULONG    TypeId,
  [in, out, optional] PULONG64 CacheCookie
);
````


## -parameters
<dl>

### -param <i>Type</i> [in]

<dd>
<p>The type name for the list items.  <i>Type</i> can include a module qualifier (for example, <b>mymodule!mytype</b>).  If <i>TypeId</i> is not zero, <i>Type</i> is not used.</p>
</dd>

### -param <i>LinkField</i> [in]

<dd>
<p>The name of the field of the typed data structure  that contains the pointer to the next list item.  This is either the SINGLE_LIST_ENTRY structure or the LIST_ENTRY structure embedded in the list item.</p>
</dd>

### -param <i>TypeModBase</i> [in]

<dd>
<p>The location in the target's memory of the base address of the module that contains the type specified by <i>TypeId</i>.  If <i>TypeId</i> is zero, <i>TypeModBase</i> is not used.</p>
</dd>

### -param <i>TypeId</i> [in]

<dd>
<p>The type ID of the type relative to the module specified by <i>TypeModBase</i>.  If <i>TypeId</i> is zero, <i>Type</i> is used to specify the type of the list items.</p>
</dd>

### -param <i>CacheCookie</i> [in, out, optional]

<dd>
<p>The cache cookie to use for caching the type information.  If <i>CacheCookie</i> is <b>NULL</b>, the debugger engine will search for the type information each time.</p>
<p>For more information about <i>CacheCookie</i>, see the <a href="https://msdn.microsoft.com/bfeafa09-49b7-45b3-84d8-afad5f43b78e">ExtRemoteTyped::Copy(Debug Typed Data)</a> or <a href="https://msdn.microsoft.com/7cc91411-3332-4a33-8873-832f71fd3281">ExtRemoteTyped::Copy(ExtRemoteTyped)</a> methods.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>For more information about the SINGLE_LIST_ENTRY and LIST_ENTRY structures, see the Windows Driver Kit documentation.</p>

<p>For more information about the SINGLE_LIST_ENTRY and LIST_ENTRY structures, see the Windows Driver Kit documentation.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544181">ExtRemoteTypedList</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/e75c17d2-fdf7-4dba-9892-74c764956924">ExtRemoteTyped::Set(bool)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/a19d6aff-c4e4-4188-8f27-3689e91023b4">ExtRemoteTyped::Set(pcstr)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/acf789f7-781d-4078-90cc-79b0d2709696">ExtRemoteTyped::Set(pcstr ulong64)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/fc3d8d9c-0b19-42b3-b4d7-90df4667739b">ExtRemoteTyped::Set(pcstr ulong64 bool)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteTypedList.SetTypeAndLink method%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
