---
UID: NF:ntifs.SeUnlockSubjectContext
title: SeUnlockSubjectContext function
author: windows-driver-content
description: The SeUnlockSubjectContext routine unlocks the tokens of a captured subject context that were locked by a call to SeLockSubjectContext.
old-location: ifsk\seunlocksubjectcontext.htm
old-project: ifsk
ms.assetid: 5b0dda8f-52de-462b-8dab-8aed86e5dc0e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SeUnlockSubjectContext
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
req.alt-api: SeUnlockSubjectContext
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

# SeUnlockSubjectContext function



## -description
The <b>SeUnlockSubjectContext</b> routine unlocks the tokens of a captured subject context that were locked by a call to <b>SeLockSubjectContext</b>.



## -syntax

````
VOID SeUnlockSubjectContext(
  _In_ PSECURITY_SUBJECT_CONTEXT SubjectContext
);
````


## -parameters

### -param SubjectContext [in]

Pointer to a SECURITY_SUBJECT_CONTEXT structure whose tokens are to be unlocked.


## -returns
None


## -remarks
<b>SeUnlockSubjectContext</b> releases the read locks on the tokens in the captured subject context.

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
<a href="..\ntifs\nf-ntifs-secapturesubjectcontext.md">SeCaptureSubjectContext</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-selocksubjectcontext.md">SeLockSubjectContext</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seprivilegecheck.md">SePrivilegeCheck</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sereleasesubjectcontext.md">SeReleaseSubjectContext</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeUnlockSubjectContext routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

