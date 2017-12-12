---
UID: NF.wdm.SeAssignSecurityEx
title: SeAssignSecurityEx function
author: windows-driver-content
description: The SeAssignSecurityEx routine builds a self-relative security descriptor for a new object given the following optional parameters: a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.
old-location: kernel\seassignsecurityex.htm
old-project: kernel
ms.assetid: 94f6d3a3-7f0d-4f57-8240-3c4a10cf4488
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: SeAssignSecurityEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SeAssignSecurityEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
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

# SeAssignSecurityEx function



## -description
The 
   <b>SeAssignSecurityEx</b> routine builds a self-relative security descriptor for a new object given the following optional parameters: a security descriptor of the object's parent directory, an explicit security descriptor for the object, and the object type.



## -syntax

````
NTSTATUS SeAssignSecurityEx(
  _In_opt_ PSECURITY_DESCRIPTOR      ParentDescriptor,
  _In_opt_ PSECURITY_DESCRIPTOR      ExplicitDescriptor,
  _Out_    PSECURITY_DESCRIPTOR      *NewDescriptor,
  _In_opt_ GUID                      *ObjectType,
  _In_     BOOLEAN                   IsDirectoryObject,
  _In_     ULONG                     AutoInheritFlags,
  _In_     PSECURITY_SUBJECT_CONTEXT SubjectContext,
  _In_     PGENERIC_MAPPING          GenericMapping,
  _In_     POOL_TYPE                 PoolType
);
````


## -parameters

### -param ParentDescriptor [in, optional]

Pointer to the <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a> of the parent object that contains the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="wdkgloss.s#wdkgloss.sacl#wdkgloss.sacl">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="wdkgloss.d#wdkgloss.dacl#wdkgloss.dacl">DACL</a>).


### -param ExplicitDescriptor [in, optional]

Pointer to an explicit <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a> that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.


### -param NewDescriptor [out]

Receives a pointer to the returned <a href="kernel.security_descriptor">SECURITY_DESCRIPTOR</a>.  <b>SeAssignSecurityEx</b> allocates the buffer from the paged memory pool.


### -param ObjectType [in, optional]

Pointer to a GUID for the type of object being created. If the object does not have a GUID, <i>ObjectType</i> must be set to <b>NULL</b>.


### -param IsDirectoryObject [in]

Specifies whether the new object is a directory object. If <i>IsDirectoryObject</i> is set to <b>TRUE</b>, the new object is a directory object, otherwise the new object is not a directory object.


### -param AutoInheritFlags [in]

Specifies the type of automatic inheritance that is applied to access control entries (<a href="wdkgloss.a#wdkgloss.ace#wdkgloss.ace">ACE</a>) in the access control lists (<a href="wdkgloss.a#wdkgloss.acl#wdkgloss.acl">ACL</a>) specified by <i>ParentDescriptor</i>. <i>AutoInheritFlags</i> also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>. <i>AutoInheritFlags</i> must be set to a logical OR of one or more of the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
SEF_DACL_AUTO_INHERIT

</td>
<td>
ACEs in the DACL of <i>ParentDescriptor</i> are inherited by <i>NewDescripto</i>r, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_SACL_AUTO_INHERIT

</td>
<td>
ACEs in the SACL of <i>ParentDescriptor</i> are inherited by <i>NewDescriptor</i>, in addition to explicit ACEs specified by <i>ExplicitDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT

</td>
<td>
<i>ExplicitDescriptor</i> is the default descriptor for the object type specified by <i>ObjectType</i>. <i>ExplicitDescriptor</i> is not used if ACEs are inherited from <i>ParentDescriptor</i>.

</td>
</tr>
<tr>
<td>
SEF_AVOID_PRIVILEGE_CHECK

</td>
<td>
Privilege checking is not done. This flag is useful with automatic inheritance because it avoids privilege checking on each child that needs to be updated. 

</td>
</tr>
<tr>
<td>
SEF_AVOID_OWNER_CHECK

</td>
<td>
Owner checking is not done.

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_OWNER_FROM_PARENT

</td>
<td>
If an owner is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the owner of <i>NewDescriptor</i> is set to the owner specified by <i>ExplictDescriptor</i>.

If an owner is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the owner of <i>NewDescriptor</i> is set to the owner of <i>ParentDescriptor</i>. Otherwise, the owner of <i>NewDescriptor</i> is set to the owner specified by the <i>SubjectContext.</i>

</td>
</tr>
<tr>
<td>
SEF_DEFAULT_GROUP_FROM_PARENT

</td>
<td>
If a group is specified by <i>ExplicitDescriptor</i>, this flag is not used, and the group of <i>NewDescriptor</i> is set to the group specified by <i>ExplictDescriptor</i>.

If a group is not specified by <i>ExplicitDescriptor</i>, this flag is used in the following way: If the flag is set, the group of <i>NewDescriptor</i> is set to the group of <i>ParentDescriptor</i>. Otherwise, the group of <i>NewDescriptor</i> is set to the group specified by the <i>SubjectContext.</i>

</td>
</tr>
</table>
 

The assignment of system and discretionary ACLs is described in the following table:

<table>
<tr>
<th></th>
<th>Nondefault explicit descriptor(1)</th>
<th>Default explicit descriptor(2)</th>
<th><b>NULL</b> Explicit descriptor</th>
</tr>
<tr>
<td>
ACL is inherited from parent descriptor(3).

</td>
<td>
Assign both inherited and explicit ACLs(5)(6).

</td>
<td>
Assign inherited ACL.

</td>
<td>
Assign inherited ACL.

</td>
</tr>
<tr>
<td>
ACL is not inherited from parent descriptor(4).

</td>
<td>
Assign nondefault ACL.

</td>
<td>
Assign default ACL.

</td>
<td>
Assign no ACL.

</td>
</tr>
</table>
 

<b>Assignment Notes</b>

<ol>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is not specified.

</li>
<li>
The SEF_DEFAULT_DESCRIPTOR_FOR_OBJECT flag is specified.

</li>
<li>
The auto inherit flag for an ACL is specified (SEF_DACL_AUTO_INHERIT or SEF_SACL_AUTO_INHERIT).

</li>
<li>
The automatic inherit flag for an ACL is not specified.

</li>
<li>
ACEs with the INHERITED_ACE bit set in their <b>AceFlags</b> member are <u>not</u> copied to the assigned security descriptor. 

</li>
<li>
ACEs that are inherited from the parent descriptor are appended after the ACEs specified by the explicit descriptor.

</li>
</ol>

### -param SubjectContext [in]

Pointer to a security context of the subject that is creating the object. <i>SubjectContext</i> is used to retrieve default security information for the new object, including the default owner, the primary group, and discretionary access control.


### -param GenericMapping [in]

Pointer to an array of access mask values that specify the mapping between each generic rights to object-specific rights.


### -param PoolType [in]

This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.


## -returns
<b>SeAssignSecurityEx</b> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The assignment was successful.
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>The SID provided as the owner of the new security descriptor is not a SID that the caller is authorized to assign as the owner of an object. 
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified SACL.

 


## -remarks
<b>SeAssignSecurityEx</b> extends the basic operation of <b>SeAssignSecurity</b> in the following ways:

<i>ObjectType</i> optionally specifies an object type. Object-specific inheritance is controlled by the following members of an object-specific ACE: <b>Flags</b>, <b>InheritedObjectType</b>, and <b>Header.AceFlags</b>.

<i>AutoInheritFlags </i>specifies the type of automatic inheritance of ACEs that is used. AutoInheritFlags also controls privilege checking, owner checking, and setting a default owner and group for <i>NewDescriptor</i>.

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
Version

</th>
<td width="70%">
Available starting with Windows 2000.

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
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.seassignsecurity">SeAssignSecurity</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeAssignSecurityEx routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

