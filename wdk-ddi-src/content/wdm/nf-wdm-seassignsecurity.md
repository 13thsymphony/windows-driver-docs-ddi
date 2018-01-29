---
UID : NF:wdm.SeAssignSecurity
title : SeAssignSecurity function
author : windows-driver-content
description : The SeAssignSecurity routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.
old-location : kernel\seassignsecurity.htm
old-project : kernel
ms.assetid : 08f0b4c0-ba77-450d-8b93-73231bbf760c
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : wdm/SeAssignSecurity, kernel.seassignsecurity, k110_10d67a00-4643-4d40-b9a2-1a19e79dc755.xml, SeAssignSecurity routine [Kernel-Mode Driver Architecture], SeAssignSecurity
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# SeAssignSecurity function
The 
   <b>SeAssignSecurity</b> routine builds a self-relative security descriptor for a new object, given the security descriptor of its parent directory and any originally requested security for the object.

## Syntax

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

## Parameters

`ParentDescriptor`

Pointer to a buffer containing the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> for the parent directory, if any, containing the new object being created. <i>ParentDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> system access control list (<a href="https://msdn.microsoft.com/5f6fec1a-1134-4765-81be-9b50939e5e66">SACL</a>) or a <b>NULL</b> discretionary access control list (<a href="https://msdn.microsoft.com/86688b5d-575d-42e1-9158-7ffba1aaf1d3">DACL</a>).

`ExplicitDescriptor`

Pointer to a buffer containing the <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a> specified by the user that is applied to the new object. <i>ExplicitDescriptor</i> can be <b>NULL</b>, or have a <b>NULL</b> SACL or a <b>NULL</b> DACL.

`NewDescriptor`

Receives a pointer to the returned <a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>. <b>SeAssignSecurity</b> allocates the buffer from the paged memory pool.

`IsDirectoryObject`

Specifies whether the new object is a directory object. <b>TRUE</b> indicates the object contains other objects.

`SubjectContext`

Pointer to a buffer containing the security context of the subject creating the object. This is used to retrieve default security information for the new object, such as the default owner, the primary group, and discretionary access control.

`GenericMapping`

Pointer to the <a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a> structure that describes the mapping from each generic right to the implied nongeneric rights.

`PoolType`

This parameter is unused.  The buffer to hold the new security descriptor is always allocated from paged pool.


## Return Value

<b>SeAssignSecurity</b> can return one of the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The assignment was successful. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>
</td>
<td width="60%">
The SID provided for the owner of the target security descriptor is not one the caller is authorized to assign as the owner of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PRIVILEGE_NOT_HELD</b></dt>
</dl>
</td>
<td width="60%">
The caller does not have the privilege (<b>SeSecurityPrivilege</b>) necessary to explicitly assign the specified system ACL.

</td>
</tr>
</table>

## Remarks

The final security descriptor returned to the caller may contain a mix of information, some explicitly provided from the new object's parent.

<b>SeAssignSecurity</b> assumes privilege checking has not been performed. This routine performs privilege checking.

The assignment of system and discretionary ACLs is governed by the logic illustrated in the following table:
<table>
<tr>
<th></th>
<th>Explicit (nondefault) ACL specified</th>
<th>Explicit default ACL specified</th>
<th>No ACL specified</th>
</tr>
<tr>
<td>
<b>Inheritable ACL from parent
              </b>

</td>
<td>
Assign specified ACL

</td>
<td>
Assign inherited ACL

</td>
<td>
Assign inherited ACL

</td>
</tr>
<tr>
<td>
<b>No inheritable ACL from parent</b>

</td>
<td>
Assign specified ACL

</td>
<td>
Assign default ACL

</td>
<td>
Assign no ACL

</td>
</tr>
</table> 

An explicitly specified ACL, whether a default ACL or not, can be empty or null. The caller must be a kernel-mode client or be appropriately privileged to explicitly assign a default or nondefault system ACL.

The assignment of the new object's owner and group is governed by the following logic:
<ul>
<li>
If the passed security descriptor includes an owner, it is assigned as the new object's owner. Otherwise, the caller's token is considered to determine the owner. Within the token, the default owner, if any, is assigned. Otherwise, the caller's user ID is assigned.

</li>
<li>
If the passed security descriptor includes a group, it is assigned as the new object's group. Otherwise, the caller's token is considered to determine the group. Within the token, the default group, if any, is assigned. Otherwise, the caller's primary group ID is assigned.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-sedeassignsecurity.md">SeDeassignSecurity</a>

<a href="..\wdm\ns-wdm-_generic_mapping.md">GENERIC_MAPPING</a>

<a href="..\ntddk\nf-ntddk-iogetfileobjectgenericmapping.md">IoGetFileObjectGenericMapping</a>

<a href="..\ntifs\ns-ntifs-_security_descriptor.md">SECURITY_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SeAssignSecurity routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>