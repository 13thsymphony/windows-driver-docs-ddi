---
UID: NF.wdm.SeAccessCheck
title: SeAccessCheck function
author: windows-driver-content
description: The SeAccessCheck routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.
old-location: kernel\seaccesscheck.htm
old-project: kernel
ms.assetid: 90726c66-738f-416f-993a-84cbf2eb67d2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: SeAccessCheck
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeAccessCheck
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# SeAccessCheck function



## -description

   The <b>SeAccessCheck</b> routine determines whether the requested access rights can be granted to an object protected by a security descriptor and an object owner.


## -syntax

````
BOOLEAN SeAccessCheck(
  _In_  PSECURITY_DESCRIPTOR      SecurityDescriptor,
  _In_  PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext,
  _In_  BOOLEAN                   SubjectContextLocked,
  _In_  ACCESS_MASK               DesiredAccess,
  _In_  ACCESS_MASK               PreviouslyGrantedAccess,
  _Out_ PPRIVILEGE_SET            *Privileges,
  _In_  PGENERIC_MAPPING          GenericMapping,
  _In_  KPROCESSOR_MODE           AccessMode,
  _Out_ PACCESS_MASK              GrantedAccess,
  _Out_ PNTSTATUS                 AccessStatus
);
````


## -parameters

### -param SecurityDescriptor [in]

Pointer to the <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a> structure that describes the security descriptor protecting the object being accessed. 

### -param SubjectSecurityContext [in]

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a> structure that specifies the subject's captured security context.

### -param SubjectContextLocked [in]

Indicates whether the user's subject context is locked, so that it does not have to be locked again.

### -param DesiredAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmask for the access rights that the caller is attempting to acquire.  If the caller sets the MAXIMUM_ALLOWED bit, the routine performs all DACL checks. However, the routine does not do any privilege checks, unless the caller specifically requests them by setting the ACCESS_SYSTEM_SECURITY or WRITE_OWNER bits.

### -param PreviouslyGrantedAccess [in]

Specifies the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> bitmask of access rights already granted, such as access rights granted as a result of holding a privilege.

### -param Privileges [out]

Pointer to a caller-supplied variable to be set to the address of the <a href="kernel.privilege_set">PRIVILEGE_SET</a> structure that will be used as part of the access validation, or this parameter can be <b>NULL</b>. The returned buffer, if any, must be released by the caller with <a href="kernel.sefreeprivileges">SeFreePrivileges</a>.

### -param GenericMapping [in]

Pointer to the <a href="kernel.generic_mapping">GENERIC_MAPPING</a> structure associated with this object type. This value specifies the specific access rights implied by each GENERIC_<i>XXX</i> access right.

### -param AccessMode [in]

Specifies the access mode to be used in the check, either <b>UserMode</b> or <b>KernelMode</b>.

### -param GrantedAccess [out]

Pointer to a returned access mask indicating the granted access. If the caller specifies MAXIMUM_ALLOWED, and the DACL in <i>SecurityDescriptor</i> is <b>NULL</b>, then the routine returns GENERIC_ALL plus any additional access the caller explicitly requests.

### -param AccessStatus [out]

Pointer to the status value indicating why access was denied.

## -returns
If access is allowed, <b>SeAccessCheck</b> returns <b>TRUE</b>.

## -remarks
<b>SeAccessCheck</b> might perform privilege tests for <b>SeTakeOwnershipPrivilege</b> and <b>SeSecurityPrivilege</b>, depending on the accesses being requested. It might perform additional privilege testing in future releases of the operating system.

This routine also might check whether the caller is the owner of the object in order to grant WRITE_DAC or READ_CONTROL access.

If this routine returns <b>FALSE</b>, the caller should use the returned <i>AccessStatus</i> as its return value. That is, the caller should avoid hardcoding a return value of STATUS_ACCESS_DENIED or any other specific STATUS_<i>XXX</i> value. 

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
Version
</th>
<td width="70%">
Available in Windows 2000 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.sefreeprivileges">SeFreePrivileges</a>
</dt>
<dt>
<a href="kernel.iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>
</dt>
<dt>
<a href="kernel.sevalidsecuritydescriptor">SeValidSecurityDescriptor</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.generic_mapping">GENERIC_MAPPING</a>
</dt>
<dt>
<a href="kernel.privilege_set">PRIVILEGE_SET</a>
</dt>
<dt>
<a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff563714">SECURITY_SUBJECT_CONTEXT</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeAccessCheck routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
