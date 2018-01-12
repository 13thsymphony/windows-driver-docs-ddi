---
UID: NF:ntifs.SeAuditingFileOrGlobalEvents
title: SeAuditingFileOrGlobalEvents function
author: windows-driver-content
description: The SeAuditingFileOrGlobalEvents routine determines whether file or global events are currently being audited.
old-location: ifsk\seauditingfileorglobalevents.htm
old-project: ifsk
ms.assetid: 4797126f-c27d-4951-88e7-37c5a475e77d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeAuditingFileOrGlobalEvents
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
req.alt-api: SeAuditingFileOrGlobalEvents
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
req.typenames: TOKEN_TYPE
---

# SeAuditingFileOrGlobalEvents function



## -description
The <b>SeAuditingFileOrGlobalEvents</b> routine determines whether file or global events are currently being audited.



## -syntax

````
BOOLEAN SeAuditingFileOrGlobalEvents(
  _In_ BOOLEAN                   AccessGranted,
  _In_ PSECURITY_DESCRIPTOR      SecurityDescriptor,
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext
);
````


## -parameters

### -param AccessGranted [in]

Set to <b>TRUE</b> if the access attempt was successful, <b>FALSE</b> otherwise.


### -param SecurityDescriptor [in]

Pointer to the security descriptor protecting the object being accessed. 


### -param SubjectSecurityContext [in]

Pointer to the subject's captured security context.


## -returns
<b>SeAuditingFileOrGlobalEvents</b> returns <b>TRUE</b> if file or global events are currently being audited, <b>FALSE</b> otherwise.


## -remarks
For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


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
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-seauditingfileevents.md">SeAuditingFileEvents</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sedeleteobjectauditalarm.md">SeDeleteObjectAuditAlarm</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seopenobjectauditalarm.md">SeOpenObjectAuditAlarm</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seopenobjectfordeleteauditalarm.md">SeOpenObjectForDeleteAuditAlarm</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeAuditingFileOrGlobalEvents routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

