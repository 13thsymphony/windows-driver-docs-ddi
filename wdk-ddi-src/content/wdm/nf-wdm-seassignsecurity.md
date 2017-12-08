---
UID: NF.wdm.SeAssignSecurity
title: SeAssignSecurity function
author: windows-driver-content
description: The SeAssignSecurity routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.
old-location: kernel\seassignsecurity.htm
old-project: kernel
ms.assetid: 08f0b4c0-ba77-450d-8b93-73231bbf760c
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: SeAssignSecurity
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
req.alt-api: SeAssignSecurity
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

# SeAssignSecurity function



## -description
The 
   <b>SeAssignSecurity</b> routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.


## -syntax

````
NTSTATUS SeAssignSecurity(
  _In_opt_ PSECURITY_DESCRIPTOR      ParentDescriptor,
  _In_opt_ PSECURITY_DESCRIPTOR      ExplicitDescriptor,
  _Out_    PSECURITY_DESCRIPTOR      *NewDescriptor,
  _In_     BOOLEAN                   IsDirectoryObject,
  _In_     PSECURITY_SUBJECT_CONTEXT SubjectContext,
  _In_     PGENERIC_MAPPING          GenericMapping,
  _In_     POOL_TYPE                 PoolType
);
````


## -parameters

### -param ParentDescriptor [in, optional]

Pointer to a buffer containing the <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a> for the parent directory, if any, containing the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="wdkgloss.s#wdkgloss.sacl#wdkgloss.sacl">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="https://msdn.microsoft.com/e4d53375-c82e-493b-9ccb-444c211fbc79">DACL</a>).

### -param ExplicitDescriptor [in, optional]

Pointer to a buffer containing the <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a> specified by the user that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.

### -param NewDescriptor [out]

Receives a pointer to the returned <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a>. <b>SeAssignSecurity</b> allocates the buffer from the paged memory pool.

### -param IsDirectoryObject [in]

Specifies whether the new object is a directory object. <b>TRUE</b> indicates the object contains other objects.

### -param SubjectContext [in]

Pointer to a buffer containing the security context of the subject creating the object. This is used to retrieve default security information for the new object, such as the default owner, the primary group, and discretionary access control.

### -param GenericMapping [in]

Pointer to the <a href="kernel.generic_mapping">GENERIC_MAPPING</a> structure that describes the mapping from each generic right to the implied nongeneric rights.

### -param PoolType [in]

This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.

## -returns
<b>SeAssignSecurity</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The assignment was successful. 
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>The SID provided for the owner of the target security descriptor is not one the caller is authorized to assign as the owner of an object.
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified system ACL.

 

## -remarks
The final security descriptor returned to the caller may contain a mix of information, some explicitly provided from the new object's parent.

<b>SeAssignSecurity</b> assumes privilege checking has not been performed. This routine performs privilege checking.

The assignment of system and discretionary ACLs is governed by the logic illustrated in the following table:

<b>Inheritable ACL from parent
              </b>

Assign specified ACL

Assign inherited ACL

<b>No inheritable ACL from parent</b>

Assign default ACL

Assign no ACL

An explicitly specified ACL, whether a default ACL or not, can be empty or null. The caller must be a kernel-mode client or be appropriately privileged to explicitly assign a default or nondefault system ACL.

The assignment of the new object's owner and group is governed by the following logic:

If the passed security descriptor includes an owner, it is assigned as the new object's owner. Otherwise, the caller's token is considered to determine the owner. Within the token, the default owner, if any, is assigned. Otherwise, the caller's user ID is assigned.

If the passed security descriptor includes a group, it is assigned as the new object's group. Otherwise, the caller's token is considered to determine the group. Within the token, the default group, if any, is assigned. Otherwise, the caller's primary group ID is assigned.

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
<a href="kernel.iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>
</dt>
<dt>
<a href="kernel.sedeassignsecurity">SeDeassignSecurity</a>
</dt>
<dt>
<a href="kernel.generic_mapping">GENERIC_MAPPING</a>
</dt>
<dt>
<a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeAssignSecurity routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
