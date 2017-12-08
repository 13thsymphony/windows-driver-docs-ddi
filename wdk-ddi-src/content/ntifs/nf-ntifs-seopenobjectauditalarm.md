---
UID: NF.ntifs.SeOpenObjectAuditAlarm
title: SeOpenObjectAuditAlarm function
author: windows-driver-content
description: The SeOpenObjectAuditAlarm routine generates audit and alarm messages when an attempt is made to open an object.
old-location: ifsk\seopenobjectauditalarm.htm
old-project: ifsk
ms.assetid: a4310cf8-1518-4d25-b2f9-a232ddd9c535
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: SeOpenObjectAuditAlarm
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
req.alt-api: SeOpenObjectAuditAlarm
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

# SeOpenObjectAuditAlarm function



## -description
The <b>SeOpenObjectAuditAlarm</b> routine generates audit and alarm messages when an attempt is made to open an object.


## -syntax

````
VOID SeOpenObjectAuditAlarm(
  _In_     PUNICODE_STRING      ObjectTypeName,
  _In_opt_ PVOID                Object,
  _In_opt_ PUNICODE_STRING      AbsoluteObjectName,
  _In_     PSECURITY_DESCRIPTOR SecurityDescriptor,
  _In_     PACCESS_STATE        AccessState,
  _In_     BOOLEAN              ObjectCreated,
  _In_     BOOLEAN              AccessGranted,
  _In_     KPROCESSOR_MODE      AccessMode,
  _Out_    PBOOLEAN             GenerateOnClose
);
````


## -parameters

### -param ObjectTypeName [in]

Pointer to a null-terminated string specifying the type of object to which the client is requesting access. This string appears in any audit message that is generated.

### -param Object [in, optional]

Address of the object being opened. This value is needed only to enter into log messages. If the open attempt fails, the value of <i>Object</i> is ignored. Otherwise, it must be provided.

### -param AbsoluteObjectName [in, optional]

Pointer to a null-terminated string specifying the name of the object being opened. This string appears in any audit message that is generated.

### -param SecurityDescriptor [in]

A pointer to the security descriptor structure for the object being opened.

### -param AccessState [in]

Pointer to an access state structure containing the object's subject context, remaining desired access types, granted access types, and, optionally, a privilege set to indicate which privileges were used to permit the access.

### -param ObjectCreated [in]

Set to <b>TRUE</b> if the open operation causes a new object to be created, or <b>FALSE</b> if an existing object is opened.

### -param AccessGranted [in]

Set to <b>TRUE</b> if open access was granted based on a previous access check or privilege check, or <b>FALSE</b> if it was denied.

### -param AccessMode [in]

Access mode used for the access check. Either <b>UserMode</b> or <b>KernelMode</b>.

### -param GenerateOnClose [out]

Pointer to a flag set by the audit generation routine when <b>SeOpenObjectAuditAlarm</b> returns.  

## -returns
None

## -remarks
<b>SeOpenObjectAuditAlarm</b> generates any necessary audit or alarm messages for user-mode accesses. No messages are generated for kernel-mode accesses.

Before calling <b>SeOpenObjectAuditAlarm</b>, the caller must call <b>SeLockSubjectContext</b> to lock the caller's primary and impersonation tokens. After calling <b>SeOpenObjectAuditAlarm</b>, the caller must call <b>SeUnlockSubjectContext</b> to release these tokens.

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
<a href="ifsk.access_state">ACCESS_STATE</a>
</dt>
<dt>
<a href="ifsk.seauditingfileevents">SeAuditingFileEvents</a>
</dt>
<dt>
<a href="ifsk.seauditingfileorglobalevents">SeAuditingFileOrGlobalEvents</a>
</dt>
<dt>
<a href="ifsk.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="ifsk.sedeleteobjectauditalarm">SeDeleteObjectAuditAlarm</a>
</dt>
<dt>
<a href="ifsk.selocksubjectcontext">SeLockSubjectContext</a>
</dt>
<dt>
<a href="ifsk.seopenobjectfordeleteauditalarm">SeOpenObjectForDeleteAuditAlarm</a>
</dt>
<dt>
<a href="ifsk.sesetaccessstategenericmapping">SeSetAccessStateGenericMapping</a>
</dt>
<dt>
<a href="ifsk.seunlocksubjectcontext">SeUnlockSubjectContext</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeOpenObjectAuditAlarm routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
