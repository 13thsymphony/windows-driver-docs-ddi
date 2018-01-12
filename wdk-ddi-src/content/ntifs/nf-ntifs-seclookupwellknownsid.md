---
UID: NF:ntifs.SecLookupWellKnownSid
title: SecLookupWellKnownSid function
author: windows-driver-content
description: SecLookupWellKnownSid accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.
old-location: ifsk\seclookupwellknownsid.htm
old-project: ifsk
ms.assetid: fbf06a28-d6f8-424c-95e0-ce24653cac64
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: SecLookupWellKnownSid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This SecLookupWellKnownSid function is only available starting with Windows Server 2003.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SecLookupWellKnownSid
req.alt-loc: Ksecdd.lib,Ksecdd.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ksecdd.lib
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: TOKEN_TYPE
---

# SecLookupWellKnownSid function



## -description
<b>SecLookupWellKnownSid</b> accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.



## -syntax

````
NTSTATUS SecLookupWellKnownSid(
  _In_    WELL_KNOWN_SID_TYPE SidType,
  _Out_   PSID                Sid,
  _In_    ULONG               SidBufferSize,
  _Inout_ PULONG              SidSize
);
````


## -parameters

### -param SidType [in]

An enumerated type that indicates the type of security identifier (SID) the function returns. This parameter can be one of the following enumerations for WELL_KNOWN_SID_TYPE:




### -param WinNullSid

This value indicates a null SID. 


### -param WinWorldSid

This value indicates a SID that matches everyone.


### -param WinLocalSid

This value indicates a local SID.


### -param WinCreatorOwnerSid 

This value indicates a SID that matches the owner or creator of an object. This SID is used in inheritable access-control entries.


### -param WinCreatorGroupSid

This value indicates a SID that matches the creator group of an object. This SID is used in inheritable access-control entries.


### -param WinCreatorOwnerServerSid

This value indicates a creator owner server SID. 


### -param WinCreatorGroupServerSid

This value indicates a creator group server SID.


### -param WinNtAuthoritySid

This value indicates a SID for the Windows NT authority.


### -param WinDialupSid

This value indicates a SID for a dial-up account.


### -param WinNetworkSid

This value indicates a SID for a network account. This SID is added to the process of a token when it logs on across a network. The corresponding logon type is LOGON32_LOGON_NETWORK. 


### -param WinBatchSid

This value indicates a SID for a batch process. This SID is added to the process of a token when it logs on as a batch job. The corresponding logon type is LOGON32_LOGON_BATCH. 


### -param WinInteractiveSid

This value indicates a SID for an interactive account. This SID is added to the process of a token when it logs on interactively. The corresponding logon type is LOGON32_LOGON_INTERACTIVE. 


### -param WinServiceSid

This value indicates a SID for a service. This SID is added to the process of a token when it logs on as a service. The corresponding logon type is LOGON32_LOGON_SERVICE. 


### -param WinAnonymousSid

This value indicates a SID for the anonymous account. 


### -param WinProxySid

This value indicates a proxy SID. 


### -param WinEnterpriseControllersSid

This value indicates a SID for an enterprise controller.


### -param WinSelfSid

This value indicates a SID for self.


### -param WinAuthenticatedUserSid

This value indicates a SID that matches any authenticated user.


### -param WinRestrictedCodeSid

This value indicates a SID for restricted code.


### -param WinTerminalServerSid

This value indicates a SID that matches a terminal server account.


### -param WinRemoteLogonIdSid

This value indicates a SID that matches remote logons.


### -param WinLogonIdsSid

This value indicates a SID that matches logon IDs.


### -param WinLocalSystemSid

This value indicates a SID that matches the local system.


### -param WinLocalServiceSid

This value indicates a SID that matches a local service.


### -param WinNetworkServiceSid

This value indicates a SID that matches a network service.


### -param WinBuiltinDomainSid

This value indicates a SID that matches the domain account.


### -param WinBuiltinAdministratorsSid

This value indicates a SID that matches the administrator account.


### -param WinBuiltinUsersSid

This value indicates a SID that matches built-in user accounts. 


### -param WinBuiltinGuestsSid

This value indicates a SID that matches the guest account.


### -param WinBuiltinPowerUsersSid

This value indicates a SID that matches the power users group.


### -param WinBuiltinAccountOperatorsSid

This value indicates a SID that matches the account operators account.


### -param WinBuiltinSystemOperatorsSid

This value indicates a SID that matches the system operators group.


### -param WinBuiltinPrintOperatorsSid

This value indicates a SID that matches the print operators group.


### -param WinBuiltinBackupOperatorsSid

This value indicates a SID that matches the backup operators group.


### -param WinBuiltinReplicatorSid

This value indicates a SID that matches the replicator account.


### -param WinBuiltinPreWindows2000CompatibleAccessSid

This value indicates a SID that matches pre-Windows 2000 compatible accounts.


### -param WinBuiltinRemoteDesktopUsersSid

This value indicates a SID that matches remote desktop users.


### -param WinBuiltinNetworkConfigurationOperatorsSid

This value indicates a SID that matches the network operators group.


### -param WinAccountAdministratorSid

This value indicates a SID that matches the account administrators group.


### -param WinAccountGuestSid

This value indicates a SID that matches the account guest group.


### -param WinAccountKrbtgtSid

This value indicates a SID that matches account Kerberos target group.


### -param WinAccountDomainAdminsSid

This value indicates a SID that matches the account domain administrator group.


### -param WinAccountDomainUsersSid

This value indicates a SID that matches the account domain users group.


### -param WinAccountDomainGuestsSid

This value indicates a SID that matches the account domain guests group.


### -param WinAccountComputersSid

This value indicates a SID that matches the account computer group.


### -param WinAccountControllersSid

This value indicates a SID that matches the account controller group.


### -param WinAccountCertAdminsSid

This value indicates a SID that matches the certificate administrators group. 


### -param WinAccountSchemaAdminsSid

This value indicates a SID that matches the schema administrators group.


### -param WinAccountEnterpriseAdminsSid

This value indicates a SID that matches the enterprise administrators group.


### -param WinAccountPolicyAdminsSid

This value indicates a SID that matches the policy administrators group.


### -param WinAccountRasAndIasServersSid

This value indicates a SID that matches the RAS and IAS server account.


### -param WinNTLMAuthenticationSid

This value indicates a SID present when the Microsoft NTLM authentication package authenticated the client.


### -param WinDigestAuthenticationSid

This value indicates a SID present when the Microsoft Digest authentication package authenticated the client.


### -param WinSChannelAuthenticationSid

This value indicates a SID present when the Secure Channel (SSL/TLS) authentication package authenticated the client.


### -param WinThisOrganizationSid

This value indicates a SID present when the user authenticated from within the forest or across a trust that does not have the selective authentication option enabled. If this SID is present, then WinOtherOrganizationSid cannot be present.


### -param WinOtherOrganizationSid

This value indicates a SID present when the user authenticated across a forest with the selective authentication option enabled. If this SID is present, then WinThisOrganizationSid cannot be present.


### -param WinBuiltinIncomingForestTrustBuildersSid

This value indicates a SID that allows a user to create incoming forest trusts. It is added to the token of users who are a member of the Incoming Forest Trust Builders built-in group in the root domain of the forest.


### -param WinBuiltinPerfMonitoringUsersSid

This value indicates a SID that matches the performance monitor user group.


### -param WinBuiltinPerfLoggingUsersSid

This value indicates a SID that matches the performance log user group.


### -param WinBuiltinAuthorizationAccessSid

This value indicates a SID that matches the Windows Authorization Access group.


### -param WinBuiltinTerminalServerLicenseServersSid

This value indicates a SID is present in a server that can issue Terminal Server licenses.


### -param WinBuiltinDCOMUsersSid

This value indicates a SID that matches the DCOM users group.

</dd>
</dl>

### -param Sid [out]


      A pointer to a buffer that receives the SID structure that corresponds to the <i>SidType</i> parameter. If this parameter is <b>NULL</b>, <i>SidBufferSize</i> must be zero. 
     


### -param SidBufferSize [in]

A variable that specifies the size of the <i>Sid</i> buffer in bytes.


### -param SidSize [in, out]

An optional pointer to a variable that specifies the size of the <i>Sid</i> buffer. If the function fails because the buffer is too small or if <i>SidBufferSize</i> is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>Sid</i>


## -returns
<b>SecLookupWellKnownSid</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>The process ID associated with the currently executing thread does not match the current process ID. 
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The buffer size for the <i>Sid</i>, the <i>SidBufferSize</i> parameter, was too small.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>A <b>NULL</b> pointer was passed for <i>Sid</i> parameter or a well-known SID could not be found for the <i>SidType</i> specified. 
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>This process has terminated so it is not possible to establish a local procedure call (LPC) connection.

 


## -remarks
<b>SecLookupWellKnownSid</b> attempts to find a well known SID using a <i>SidType</i> parameter. In addition to looking up well-known SIDs on the local machine, <b>SecLookupWellKnownSid</b> can look up well-known SIDs on the local domain. <b>SecLookupWellKnownSid</b>first checks a list of well-known local SIDs. If the <i>SidType</i> does not correspond to a local well-known SID, the function checks for well-known SIDs on the primary domain. 

If the function cannot find the well known SID for the <i>SidType</i> specified, <b>SecLookupWellKnownSid</b> fails. This can occur if a network time-out prevents the function from finding the SID on the primary domain. It also occurs for a <i>SidType</i> that has no corresponding well-known SID.

<b>SecLookupWellKnownSid</b> is equivalent to the Win32   <b>CreateWellKnownSid</b> function. For user-mode applications, the WELL_KNOWN_SID_TYPE enumeration is defined in <i>winbase.h</i>.

<b>SecLookupWellKnownSid</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupWellKnownSid</b> cannot be used during paging file I/O. 


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
This SecLookupWellKnownSid function is only available starting with Windows Server 2003.

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
<dt>Ksecdd.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntifs\nf-ntifs-seclookupaccountname.md">SecLookupAccountName</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-seclookupaccountsid.md">SecLookupAccountSid</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SecLookupWellKnownSid function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

