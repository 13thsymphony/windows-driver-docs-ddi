---
UID: NF:ntifs.SePrivilegeCheck
title: SePrivilegeCheck function
author: windows-driver-content
description: The SePrivilegeCheck routine determines whether a specified set of privileges is enabled in the subject's access token.
old-location: ifsk\seprivilegecheck.htm
old-project: ifsk
ms.assetid: 707ced39-4153-4a6e-b87d-7e4eb487e738
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: SePrivilegeCheck, SePrivilegeCheck routine [Installable File System Drivers], ifsk.seprivilegecheck, ntifs/SePrivilegeCheck, seref_45aa3a8c-26b9-4bb9-968a-5f7d4a12ca3a.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	SePrivilegeCheck
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# SePrivilegeCheck function
The <b>SePrivilegeCheck</b> routine determines whether a specified set of privileges is enabled in the subject's access token.

## Syntax

````
BOOLEAN SePrivilegeCheck(
  _Inout_ PPRIVILEGE_SET            RequiredPrivileges,
  _In_    PSECURITY_SUBJECT_CONTEXT SubjectSecurityContext,
  _In_    KPROCESSOR_MODE           AccessMode
);
````

## Parameters

`RequiredPrivileges`

Pointer to a PRIVILEGE_SET structure. The <b>Privilege</b> member of this structure is an array of LUID_AND_ATTRIBUTES structures. Before calling <b>SePrivilegeCheck</b>, use the <b>Privilege</b> array to indicate the set of privileges to check. Set the <b>Control</b> member to PRIVILEGE_SET_ALL_NECESSARY if all of the privileges must be enabled; or set it to zero if it is sufficient that any one of the privileges be enabled. 

When <b>SePrivilegeCheck</b> returns, the <b>Attributes</b> member of each LUID_AND_ATTRIBUTES structure is set to SE_PRIVILEGE_USED_FOR_ACCESS if the corresponding privilege is enabled.

`SubjectSecurityContext`

Pointer to the subject's captured security context.

`AccessMode`

The access mode to use for the privilege check. Either <b>UserMode</b> or <b>KernelMode</b>. If <i>AccessMode</i> is set to <b>KernelMode</b>, then all privileges are marked as being possessed by the subject, and <b>SePrivilegeCheck</b> returns <b>TRUE</b>.


## Return Value

<b>SePrivilegeCheck</b> returns <b>TRUE</b> if all specified privileges are held by the subject, <b>FALSE</b> otherwise.

## Remarks

An access token contains a list of the privileges held by the account associated with the token. These privileges can be enabled or disabled; most are disabled by default. <b>SePrivilegeCheck</b> checks only for enabled privileges. To get a list of all the enabled and disabled privileges held by an access token, call <b>SeQueryInformationToken</b>. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntifs\nf-ntifs-seappendprivileges.md">SeAppendPrivileges</a>



<a href="..\wdm\ns-wdm-_privilege_set.md">PRIVILEGE_SET</a>



<a href="..\wdm\nf-wdm-seaccesscheck.md">SeAccessCheck</a>



<a href="..\wdm\ns-wdm-_security_subject_context.md">SECURITY_SUBJECT_CONTEXT</a>



<a href="..\ntddk\nf-ntddk-sesingleprivilegecheck.md">SeSinglePrivilegeCheck</a>



<a href="..\ntifs\nf-ntifs-sefreeprivileges.md">SeFreePrivileges</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>