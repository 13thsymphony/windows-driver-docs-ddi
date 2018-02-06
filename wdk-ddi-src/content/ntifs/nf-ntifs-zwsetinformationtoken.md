---
UID: NF:ntifs.ZwSetInformationToken
title: ZwSetInformationToken function
author: windows-driver-content
description: The ZwSetInformationToken routine modifies information in a specified token. The calling process must have appropriate access rights to set the information.
old-location: kernel\zwsetinformationtoken.htm
old-project: kernel
ms.assetid: fdb1245c-7804-4cb9-9632-bedb9f7f7b2b
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ZwSetInformationToken routine [Kernel-Mode Driver Architecture], ntifs/ZwSetInformationToken, k111_1122461b-dab8-4a40-8f05-db62ca25763b.xml, ZwSetInformationToken, NtSetInformationToken, ntifs/NtSetInformationToken, kernel.zwsetinformationtoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	ZwSetInformationToken
-	NtSetInformationToken
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# ZwSetInformationToken function
The <b>ZwSetInformationToken</b> routine modifies information in a specified token. The calling process must have appropriate access rights to set the information.

## Syntax

````
NTSTATUS ZwSetInformationToken(
  _In_ HANDLE                  TokenHandle,
  _In_ TOKEN_INFORMATION_CLASS TokenInformationClass,
  _In_ PVOID                   TokenInformation,
  _In_ ULONG                   TokenInformationLength
);
````

## Parameters

`TokenHandle`

Handle for an access token in which information is to be modified.

`TokenInformationClass`

A value from the <a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a> enumerated type identifying the type of information to be modified. The possible values for this parameter are listed in the <i>TokenInformationClass</i> Value column of the table shown in the description of the <i>TokenInformation</i> parameter.

`TokenInformation`

Pointer to a caller-supplied buffer containing the information to be modified in the token. The structure of the information in this buffer depends upon the value of <i>TokenInformationClass</i>, as shown in the following table. All structures must be aligned on a 32-bit boundary. 
<table>
<tr>
<th><i>TokenInformationClass</i> value</th>
<th>Effect on <i>TokenInformation</i> buffer</th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
The buffer contains a <a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a> structure specifying the default <a href="..\wdm\ns-wdm-_acl.md">DACL</a> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The buffer contents are not validated for structural correctness or consistency. 

</td>
</tr>
<tr>
<td>
<b>TokenGroups</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
The buffer contains a <a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a> structure specifying the default owner <a href="..\ntifs\ns-ntifs-_sid.md">SID</a> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. The owner values that may be specified are restricted to the user and group IDs with an attribute indicating they can be assigned as the owner of objects. 

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
The buffer contains a <a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a> structure specifying the default primary group <b>SID</b> for newly created objects. TOKEN_ADJUST_DEFAULT access is required to set this information. Must be one of the group IDs already in the token. 

</td>
</tr>
<tr>
<td>
<b>TokenPrivileges</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenSource</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenStatistics</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
<tr>
<td>
<b>TokenUser</b>

</td>
<td>
Not a valid information class. This information is read-only. 

</td>
</tr>
</table>

`TokenInformationLength`

Size, in bytes, of the structure passed in the <i>TokenInformation</i> buffer. Must be greater than or equal to the minimum value given in the following table. 
<table>
<tr>
<th><i>TokenInformationClass</i> value</th>
<th>Minimum <i>TokenInformationLength</i></th>
</tr>
<tr>
<td>
<b>TokenDefaultDacl</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_DEFAULT_DACL</b>) 

</td>
</tr>
<tr>
<td>
<b>TokenOwner</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_OWNER</b>) 

</td>
</tr>
<tr>
<td>
<b>TokenPrimaryGroup</b>

</td>
<td>
<b>sizeof</b>(<b>TOKEN_PRIMARY_GROUP</b>) 

</td>
</tr>
</table>


## Return Value

<b>ZwSetInformationToken</b> returns STATUS_SUCCESS or an appropriate error status. Possible error status codes include the following:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> did not have the required access.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ALLOTTED_SPACE_EXCEEDED</b></dt>
</dl>
</td>
<td width="60%">
The space allotted for storage of the default discretionary access control and the primary group ID is not large enough to accept the new value of one of these fields.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The value of <i>TokenInformationLength</i> was less than the required minimum.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
The specified default owner's security information could not be captured.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a valid handle.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_INFO_CLASS</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenInformationClass</i> was not a valid token information class.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_OWNER</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot set the specified ID to be an owner (or default owner) of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PRIMARY_GROUP</b></dt>
</dl>
</td>
<td width="60%">
The caller cannot set the specified ID to be the primary group of an object.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_SID</b></dt>
</dl>
</td>
<td width="60%">
The specified default owner's security information was not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_OBJECT_TYPE_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
<i>TokenHandle</i> was not a token handle.

</td>
</tr>
</table>

## Remarks

For more information about security and access control, see the documentation on these topics in the Windows SDK.
<div class="alert"><b>Note</b>  If the call to the <b>ZwSetInformationToken</b> function occurs in user mode, you should use the name "<a href="https://msdn.microsoft.com/library/windows/hardware/ff557678">NtSetInformationToken</a>" instead of "<b>ZwSetInformationToken</b>".</div><div> </div>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 7 and later versions of Windows. Available in Windows 7 and later versions of Windows. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | PowerIrpDDis, HwStorPortProhibitedDDIs |

## See Also

<a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a>

<a href="..\ntifs\nf-ntifs-psdereferenceimpersonationtoken.md">PsDereferenceImpersonationToken</a>

<a href="..\ntifs\nf-ntifs-psdereferenceprimarytoken.md">PsDereferencePrimaryToken</a>

<a href="..\ntifs\nf-ntifs-setokenisadmin.md">SeTokenIsAdmin</a>

<a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a>

<a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>

<a href="..\ntifs\nf-ntifs-sequeryauthenticationidtoken.md">SeQueryAuthenticationIdToken</a>

<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>

<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>

<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>

<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>

<a href="..\ntifs\nf-ntifs-sequerysubjectcontexttoken.md">SeQuerySubjectContextToken</a>

<a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a>

<a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>

<a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a>

<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>

<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwSetInformationToken routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>