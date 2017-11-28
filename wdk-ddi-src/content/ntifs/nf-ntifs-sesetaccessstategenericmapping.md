---
UID: NF.ntifs.SeSetAccessStateGenericMapping
title: SeSetAccessStateGenericMapping
author: windows-driver-content
description: The SeSetAccessStateGenericMapping routine sets the generic mapping field of an ACCESS_STATE structure.
old-location: ifsk\sesetaccessstategenericmapping.htm
old-project: ifsk
ms.assetid: b9a5ca5c-2d1c-4974-bef8-6003a4d6e864
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SeSetAccessStateGenericMapping
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeSetAccessStateGenericMapping
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.iface: 
---

# SeSetAccessStateGenericMapping function



## -description
<p>The <b>SeSetAccessStateGenericMapping</b> routine sets the generic mapping field of an ACCESS_STATE structure.</p>


## -syntax

````
VOID SeSetAccessStateGenericMapping(
  _Inout_ PACCESS_STATE    AccessState,
  _In_    PGENERIC_MAPPING GenericMapping
);
````


## -parameters
<dl>

### -param <i>AccessState</i> [in, out]

<dd>
<p>Pointer to the ACCESS_STATE structure to be modified.</p>
</dd>

### -param <i>GenericMapping</i> [in]

<dd>
<p>Pointer to a GENERIC<b>_</b>MAPPING structure to be copied into the ACCESS_STATE structure specified by <i>AccessState</i>. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p><b>SeSetAccessStateGenericMapping</b> sets the <b>GenericMapping</b> field in the <b>AuxData</b> member of an ACCESS_STATE structure. If this field is not set when the ACCESS_STATE structure is created, <b>SeSetAccessStateGenericMapping</b> must be called to set this field before the structure is used to perform access validation.</p>

<p>The generic mapping structure defines the mapping of generic access rights to specific and standard access rights for an object. When a client requests generic access rights to an object, the desired access mask is mapped to one of the access masks defined in this structure.</p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

<p><b>SeSetAccessStateGenericMapping</b> sets the <b>GenericMapping</b> field in the <b>AuxData</b> member of an ACCESS_STATE structure. If this field is not set when the ACCESS_STATE structure is created, <b>SeSetAccessStateGenericMapping</b> must be called to set this field before the structure is used to perform access validation.</p>

<p>The generic mapping structure defines the mapping of generic access rights to specific and standard access rights for an object. When a client requests generic access rights to an object, the desired access mask is mapped to one of the access masks defined in this structure.</p>

<p>For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff538840">ACCESS_STATE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff546526">GENERIC_MAPPING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554762">SeAppendPrivileges</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeSetAccessStateGenericMapping routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
