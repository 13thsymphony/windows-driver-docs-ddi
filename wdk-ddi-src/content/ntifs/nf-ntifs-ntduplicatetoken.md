---
UID: NF.ntifs.NtDuplicateToken
title: NtDuplicateToken
author: windows-driver-content
description: The ZwDuplicateToken function creates a handle to a new access token that duplicates an existing token. This function can create either a primary token or an impersonation token.
old-location: kernel\zwduplicatetoken.htm
old-project: kernel
ms.assetid: 89cc86aa-8ab0-4614-b92d-a1c627490d8d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NtDuplicateToken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ZwDuplicateToken,NtDuplicateToken
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
req.iface: 
---

# NtDuplicateToken function



## -description
<p>The <b>ZwDuplicateToken</b> function creates a handle to a new <a href="http://go.microsoft.com/fwlink/p/?linkid=96098">access token</a> that duplicates an existing token. This function can create either a primary token or an impersonation token. </p>


## -syntax

````
NTSTATUS ZwDuplicateToken(
  _In_  HANDLE             ExistingTokenHandle,
  _In_  ACCESS_MASK        DesiredAccess,
  _In_  POBJECT_ATTRIBUTES ObjectAttributes,
  _In_  BOOLEAN            EffectiveOnly,
  _In_  TOKEN_TYPE         TokenType,
  _Out_ PHANDLE            NewTokenHandle
);
````


## -parameters
<dl>

### -param ExistingTokenHandle [in]

<dd>
<p>A handle to an existing access token that was opened with the TOKEN_DUPLICATE access right. This parameter is required and cannot be <b>NULL</b>.</p>
</dd>

### -param DesiredAccess [in]

<dd>
<p>Bitmask that specifies the requested access rights for the new token. <b>ZwDuplicateToken</b> compares the requested access rights with the existing token's discretionary access control list (DACL) to determine which rights are granted or denied to the new token. To request the same access rights as the existing token, specify zero. To request all access rights that are valid for the caller, specify MAXIMUM_ALLOWED. This parameter is optional and can either be zero, MAXIMUM_ALLOWED, or a bitwise OR combination of one or more of the following values:</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p>DELETE</p>
</td>
<td>
<p>Required to delete the object.</p>
</td>
</tr>
<tr>
<td>
<p>READ_CONTROL</p>
</td>
<td>
<p>Required to read the DACL and ownership information for the object. For access to the system access control list (SACL), see ACCESS_SYSTEM_SECURITY later in this table.</p>
</td>
</tr>
<tr>
<td>
<p>WRITE_DAC</p>
</td>
<td>
<p>Required to change the DACL information for the object.</p>
</td>
</tr>
<tr>
<td>
<p>WRITE_OWNER</p>
</td>
<td>
<p>Required to change the ownership information in the object's security descriptor (<a href="..\ntifs\ns-ntifs--security-descriptor.md">SECURITY_DESCRIPTOR</a>).</p>
</td>
</tr>
<tr>
<td>
<p>ACCESS_SYSTEM_SECURITY</p>
</td>
<td>
<p>Required to get or set the SACL in an object's ACL. The operating system grants this right to the new token only if the SE_SECURITY_NAME privilege is enabled in the access token of the calling thread.</p>
</td>
</tr>
<tr>
<td>
<p>STANDARD_RIGHTS_READ</p>
</td>
<td>
<p>Currently defined to equal READ_CONTROL.</p>
</td>
</tr>
<tr>
<td>
<p>STANDARD_RIGHTS_WRITE</p>
</td>
<td>
<p>Currently defined to equal READ_CONTROL.</p>
</td>
</tr>
<tr>
<td>
<p>STANDARD_RIGHTS_EXECUTE</p>
</td>
<td>
<p>Currently defined to equal READ_CONTROL.</p>
</td>
</tr>
<tr>
<td>
<p>STANDARD_RIGHTS_REQUIRED</p>
</td>
<td>
<p>Combines DELETE, READ_CONTROL, WRITE_DAC, and WRITE_OWNER access.</p>
</td>
</tr>
<tr>
<td>
<p>STANDARD_RIGHTS_ALL</p>
</td>
<td>
<p>Combines DELETE, READ_CONTROL, WRITE_DAC, WRITE_OWNER, and SYNCHRONIZE access. However, the SYNCHRONIZE value is not applicable to token objects. Thus, STANDARD_RIGHTS_ALL has a  functionally equivalent to STANDARD_RIGHTS_REQUIRED.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ADJUST_DEFAULT</p>
</td>
<td>
<p>Required to change the default owner, primary group, or DACL of an access token.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ADJUST_GROUPS</p>
</td>
<td>
<p>Required to adjust the attributes of the groups in an access token.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ADJUST_PRIVILEGES</p>
</td>
<td>
<p>Required to enable or disable the privileges in an access token.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ADJUST_SESSIONID</p>
</td>
<td>
<p>Required to adjust the session ID (SID) of an access token. The operating system grants this right to the new token only if the SE_TCB_NAME privilege is enabled in the access token of the calling thread.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ASSIGN_PRIMARY</p>
</td>
<td>
<p>Required to attach a primary token to a process. The operating system grants this right to the new token only if the SE_ASSIGNPRIMARYTOKEN_NAME privilege is enabled in the access token of the calling thread.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_DUPLICATE</p>
</td>
<td>
<p>Required to duplicate an access token. Note that the given <i>ExistingTokenHandle</i> token must contain this right in order to successfully use this routine.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_EXECUTE</p>
</td>
<td>
<p>Combines STANDARD_RIGHTS_EXECUTE and TOKEN_IMPERSONATE.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_IMPERSONATE</p>
</td>
<td>
<p>Required to attach an impersonation access token to a process.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_QUERY</p>
</td>
<td>
<p>Required to query an access token.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_QUERY_SOURCE</p>
</td>
<td>
<p>Required to query the source of an access token.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_READ</p>
</td>
<td>
<p>Combines STANDARD_RIGHTS_READ and TOKEN_QUERY.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_WRITE</p>
</td>
<td>
<p>Combines STANDARD_RIGHTS_WRITE, TOKEN_ADJUST_PRIVILEGES, TOKEN_ADJUST_GROUPS, and TOKEN_ADJUST_DEFAULT.</p>
</td>
</tr>
<tr>
<td>
<p>TOKEN_ALL_ACCESS</p>
</td>
<td>
<p>Combines all possible token access permissions for a token.</p>
</td>
</tr>
</table>
<p> </p>
<p>For additional information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91036">Access Rights for Access-Token Objects</a> in the Microsoft Windows SDK. Note that access tokens do not support the SYNCHRONIZE right.</p>
</dd>

### -param ObjectAttributes [in]

<dd>
<p>Pointer to an <a href="..\d3dkmthk\ns-d3dkmthk--object-attributes.md">OBJECT_ATTRIBUTES</a> structure that describes the requested properties for the new token. The <i>ObjectAttributes</i> parameter is optional and can be <b>NULL</b>. If the <i>ObjectAttributes</i> parameter is <b>NULL</b> or if the <b>SecurityDescriptor</b> member of the structure pointed to by the <i>ObjectAttributes</i> parameter is <b>NULL</b>, the new token receives a default security descriptor and the new token handle cannot be inherited. In that case, this default security descriptor is created from the user group, primary group, and DACL information that is stored in the caller's token.</p>
<p>When the <i>TokenType</i> parameter is set to <b>TokenImpersonation</b>:</p>
<ul>
<li>
<p>The <i>ObjectAttributes </i>parameter may be used to specify the impersonation level of the new token. This can be accomplished by setting <i>ObjectAttributes</i>-&gt;SecurityQualityOfService.ImpersonationLevel to an appropriate <a href="..\wudfddi\ne-wudfddi--security-impersonation-level.md">SECURITY_IMPERSONATION_LEVEL</a> enumeration value. For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91038">SECURITY_QUALITY_OF_SERVICE</a> in the Microsoft Windows SDK documentation.</p>
</li>
<li>
<p>If the existing token is an impersonation token and the <i>ObjectAttributes</i> parameter provides no impersonation information, the new token's impersonation level is set to the existing token's impersonation level.</p>
</li>
<li>
<p>If the existing token is a primary token and no impersonation level information is provided, the new impersonation token will have a <a href="..\wudfddi\ne-wudfddi--security-impersonation-level.md">SECURITY_IMPERSONATION_LEVEL</a> impersonation level.</p>
</li>
</ul>
</dd>

### -param EffectiveOnly [in]

<dd>
<p>A Boolean value that indicates whether the entire existing token should be duplicated into the new token or just the effective (currently enabled) part of the token. If set to <b>TRUE</b>, only the currently enabled parts of the source token will be duplicated. If set to <b>FALSE</b>, the entire existing token will be duplicated. This provides a means for a caller of a protected subsystem to limit which optional groups and privileges are made available to the protected subsystem. For example, if <i>EffectiveOnly</i> is <b>TRUE</b>, the caller could duplicate a token but remove the Administrators group and the SeTcbPrivilege right. The resulting token could then be passed to a child process (<a href="http://go.microsoft.com/fwlink/p/?linkid=91041">CreateProcessAsUser</a>), which would restrict what the child process can do. This parameter is required.</p>
</dd>

### -param TokenType [in]

<dd>
<p>Specifies one of the following values from the <a href="..\ntifs\ne-ntifs--token-type.md">TOKEN_TYPE</a> enumeration.</p>
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<p><b>TokenPrimary</b></p>
</td>
<td>
<p>The new token is a primary token. If the existing token is an impersonation token, the existing impersonation token must have an impersonation level (as provided by the <i>ObjectAttributes</i> parameter) of <b>SecurityImpersonation</b> or <b>SecurityDelegation</b>. Otherwise, <b>ZwDuplicateToken</b> returns STATUS_BAD_IMPERSONATION_LEVEL is returned.</p>
</td>
</tr>
<tr>
<td>
<p><b>TokenImpersonation</b></p>
</td>
<td>
<p>The new token is an impersonation token. If the existing token is an impersonation token, the requested impersonation level (as provided by the <i>ObjectAttributes</i> parameter) of the new token must not be greater than the impersonation level of the existing token. Otherwise, <b>ZwDuplicateToken </b>returns STATUS_BAD_IMPERSONATION_LEVEL.</p>
</td>
</tr>
</table>
<p> </p>
<p>The <i>TokenType</i> parameter is required and cannot be <b>NULL</b>.</p>
</dd>

### -param NewTokenHandle [out]

<dd>
<p>A pointer to a caller-allocated variable, of type HANDLE, that receives a handle to the new token. This parameter is required and cannot be <b>NULL</b>.</p>
</dd>
</dl>

## -returns
<p><b>ZwDuplicateToken</b> returns STATUS_SUCCESS if the call is successfull. Possible error return codes include the following:</p><dl>
<dt><b>STATUS_ACCESS_VIOLATION</b></dt>
</dl><p>A memory access violation occurred. For example, if the previous mode was user-mode and invalid user-mode memory was provided, <b>ZwDuplicateToken</b> returns STATUS_ACCESS_VIOLATION. </p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>Sufficient memory could not be allocated to duplicate the new token. </p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An invalid parameter was detected. </p><dl>
<dt><b>STATUS_BAD_IMPERSONATION_LEVEL</b></dt>
</dl><p>The requested impersonation level for the new token is greater than the impersonation level of the existing token. </p><dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl><p><b>ZwDuplicateToken</b> returns STATUS_ACCESS_DENIED if it couldn't access <i>ExistingTokenHandle</i>. This would occur if the existing token does not have the TOKEN_DUPLICATE access right. </p><dl>
<dt><b>STATUS_INVALID_HANDLE</b></dt>
</dl><p><b>ZwDuplicateToken</b> returns STATUS_INVALID_HANDLE if <i>ExistingTokenHandle</i> refers to an invalid handle. </p>

<p> </p>

## -remarks
<p>If no impersonation level information was provided by the <i>ObjectAttributes</i> parameter, the existing token's impersonation level will be used for the new token.</p>

<p>With regard to the structure pointed to by the optional <i>ObjectAttributes</i> parameter, the <b>SecurityQualityOfService</b> member of <a href="..\d3dkmthk\ns-d3dkmthk--object-attributes.md">OBJECT_ATTRIBUTES</a> points to a structure of type <b>SECURITY_QUALITY_OF_SERVICE</b>. See <a href="http://go.microsoft.com/fwlink/p/?linkid=91038">SECURITY_QUALITY_OF_SERVICE</a> in the Microsoft Windows SDK documentation for information on the members of this structure.</p>

<p>For information on the user-mode analog of <b>ZwDuplicateToken</b>, see <a href="http://go.microsoft.com/fwlink/p/?linkid=91047">DuplicateTokenEx</a> in the Windows SDK documentation.</p>

<p>When you have finished using the new token, call the <a href="..\wdm\nf-wdm-zwclose.md">ZwClose</a> function to close the token handle.</p>

<p>For calls from kernel-mode drivers, the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the <b>Nt<i>Xxx</i></b> and <b>Zw<i>Xxx</i></b> versions of a routine, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565438">Using Nt and Zw Versions of the Native System Services Routines</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.wdm_powerirpddis">PowerIrpDDis</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="..\wudfwdm\nf-wudfwdm-initializeobjectattributes.md">InitializeObjectAttributes</a>
</dt>
<dt>
<a href="..\d3dkmthk\ns-d3dkmthk--object-attributes.md">OBJECT_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\wudfddi\ne-wudfddi--security-impersonation-level.md">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ZwDuplicateToken function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
