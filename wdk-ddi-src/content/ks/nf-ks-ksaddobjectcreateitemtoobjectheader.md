---
UID: NF.ks.KsAddObjectCreateItemToObjectHeader
title: KsAddObjectCreateItemToObjectHeader function
author: windows-driver-content
description: The KsAddObjectCreateItemToObjectHeader function adds the specified create-item to an empty item in the previously allocated create item list for this object header.
old-location: stream\ksaddobjectcreateitemtoobjectheader.htm
old-project: stream
ms.assetid: 9946e896-7f1a-4ff2-afa5-9e231047af11
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsAddObjectCreateItemToObjectHeader
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsAddObjectCreateItemToObjectHeader
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsAddObjectCreateItemToObjectHeader function



## -description
The <b>KsAddObjectCreateItemToObjectHeader</b> function adds the specified create-item to an empty item in the previously allocated create item list for this object header. An empty item is signified by a <b>NULL</b> create dispatch function in the entry. This function assumes that the caller is serializing multiple changes to the create items list.



## -syntax

````
NTSTATUS KsAddObjectCreateItemToObjectHeader(
  _In_     KSOBJECT_HEADER      Header,
  _In_     PDRIVER_DISPATCH     Create,
  _In_     PVOID                Context,
  _In_     PWSTR                ObjectClass,
  _In_opt_ PSECURITY_DESCRIPTOR SecurityDescriptor
);
````


## -parameters

### -param Header [in]

Points to the object header that contains the previously allocated child- create table.


### -param Create [in]

Specifies the create dispatch function to use.


### -param Context [in]

Specifies the context parameter.


### -param ObjectClass [in]

Specifies a pointer to a <b>NULL</b>-terminated character string that is used for comparison on create requests. This pointer must remain valid while the object is active.


### -param SecurityDescriptor [in, optional]

Specifies the security descriptor. This must remain valid while the object is active.


## -returns
The <b>KsAddObjectCreateItemToObjectHeader</b> function returns STATUS_SUCCESS if an empty create item slot was found and the item was added. If unsuccessful, it returns STATUS_ALLOTTED_SPACE_EXCEEDED.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>