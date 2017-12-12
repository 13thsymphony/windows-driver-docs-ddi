---
UID: NF.ntifs.SeLockSubjectContext
title: SeLockSubjectContext function
author: windows-driver-content
description: The SeLockSubjectContext routine locks the primary and impersonation tokens of a captured subject context.
old-location: ifsk\selocksubjectcontext.htm
old-project: ifsk
ms.assetid: 032e203a-9cb0-4232-91fc-883528e15a81
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SeLockSubjectContext
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
req.alt-api: SeLockSubjectContext
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
---

# SeLockSubjectContext function



## -description
The <b>SeLockSubjectContext</b> routine locks the primary and impersonation tokens of a captured subject context.



## -syntax

````
VOID SeLockSubjectContext(
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectContext
);
````


## -parameters

### -param SubjectContext [in]

Pointer to a SECURITY_SUBJECT_CONTEXT structure returned by a call to <b>SeCaptureSubjectContext</b>.


## -returns
None


## -remarks
<b>SeLockSubjectContext</b> acquires read locks on the primary and impersonation tokens of a captured subject context.

To capture a subject context, use <b>SeCaptureSubjectContext</b>.

Each call to <b>SeLockSubjectContext</b> must be matched by a subsequent call to <b>SeUnlockSubjectContext</b>.

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
<a href="ifsk.secapturesubjectcontext">SeCaptureSubjectContext</a>
</dt>
<dt>
<a href="ifsk.security_subject_context">SECURITY_SUBJECT_CONTEXT</a>
</dt>
<dt>
<a href="ifsk.seunlocksubjectcontext">SeUnlockSubjectContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeLockSubjectContext routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

