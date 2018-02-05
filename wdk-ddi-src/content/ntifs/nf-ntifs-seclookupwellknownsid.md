---
UID : NF:ntifs.SecLookupWellKnownSid
title : SecLookupWellKnownSid function
author : windows-driver-content
description : SecLookupWellKnownSid accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.
old-location : ifsk\seclookupwellknownsid.htm
old-project : ifsk
ms.assetid : fbf06a28-d6f8-424c-95e0-ce24653cac64
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : SecLookupWellKnownSid function [Installable File System Drivers], SecLookupWellKnownSid, ksecddref_4c0053b3-cdaa-4cdc-a4d3-6329ccf64f98.xml, ntifs/SecLookupWellKnownSid, ifsk.seclookupwellknownsid
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : This SecLookupWellKnownSid function is only available starting with Windows Server 2003.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ksecdd.lib
req.dll : 
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# SecLookupWellKnownSid function
<b>SecLookupWellKnownSid</b> accepts a well-known security identifier (SID) type as input and retrieves the local security identifier (SID) for this well known SID.

## Syntax

````
NTSTATUS SecLookupWellKnownSid(
  _In_    WELL_KNOWN_SID_TYPE SidType,
  _Out_   PSID                Sid,
  _In_    ULONG               SidBufferSize,
  _Inout_ PULONG              SidSize
);
````

## Parameters

`SidType`

An enumerated type that indicates the type of security identifier (SID) the function returns. This parameter can be one of the following enumerations for WELL_KNOWN_SID_TYPE:




#### WinAccountAdministratorSid

This value indicates a SID that matches the account administrators group.


#### WinAccountCertAdminsSid

This value indicates a SID that matches the certificate administrators group. 


#### WinAccountComputersSid

This value indicates a SID that matches the account computer group.


#### WinAccountControllersSid

This value indicates a SID that matches the account controller group.


#### WinAccountDomainAdminsSid

This value indicates a SID that matches the account domain administrator group.


#### WinAccountDomainGuestsSid

This value indicates a SID that matches the account domain guests group.


#### WinAccountDomainUsersSid

This value indicates a SID that matches the account domain users group.


#### WinAccountEnterpriseAdminsSid

This value indicates a SID that matches the enterprise administrators group.


#### WinAccountGuestSid

This value indicates a SID that matches the account guest group.


#### WinAccountKrbtgtSid

This value indicates a SID that matches account Kerberos target group.


#### WinAccountPolicyAdminsSid

This value indicates a SID that matches the policy administrators group.


#### WinAccountRasAndIasServersSid

This value indicates a SID that matches the RAS and IAS server account.


#### WinAccountSchemaAdminsSid

This value indicates a SID that matches the schema administrators group.


#### WinAnonymousSid

This value indicates a SID for the anonymous account. 


#### WinAuthenticatedUserSid

This value indicates a SID that matches any authenticated user.


#### WinBatchSid

This value indicates a SID for a batch process. This SID is added to the process of a token when it logs on as a batch job. The corresponding logon type is LOGON32_LOGON_BATCH. 


#### WinBuiltinAccountOperatorsSid

This value indicates a SID that matches the account operators account.


#### WinBuiltinAdministratorsSid

This value indicates a SID that matches the administrator account.


#### WinBuiltinAuthorizationAccessSid

This value indicates a SID that matches the Windows Authorization Access group.


#### WinBuiltinBackupOperatorsSid

This value indicates a SID that matches the backup operators group.


#### WinBuiltinDCOMUsersSid

This value indicates a SID that matches the DCOM users group.


#### WinBuiltinDomainSid

This value indicates a SID that matches the domain account.


#### WinBuiltinGuestsSid

This value indicates a SID that matches the guest account.


#### WinBuiltinIncomingForestTrustBuildersSid

This value indicates a SID that allows a user to create incoming forest trusts. It is added to the token of users who are a member of the Incoming Forest Trust Builders built-in group in the root domain of the forest.


#### WinBuiltinNetworkConfigurationOperatorsSid

This value indicates a SID that matches the network operators group.


#### WinBuiltinPerfLoggingUsersSid

This value indicates a SID that matches the performance log user group.


#### WinBuiltinPerfMonitoringUsersSid

This value indicates a SID that matches the performance monitor user group.


#### WinBuiltinPowerUsersSid

This value indicates a SID that matches the power users group.


#### WinBuiltinPreWindows2000CompatibleAccessSid

This value indicates a SID that matches pre-Windows 2000 compatible accounts.


#### WinBuiltinPrintOperatorsSid

This value indicates a SID that matches the print operators group.


#### WinBuiltinRemoteDesktopUsersSid

This value indicates a SID that matches remote desktop users.


#### WinBuiltinReplicatorSid

This value indicates a SID that matches the replicator account.


#### WinBuiltinSystemOperatorsSid

This value indicates a SID that matches the system operators group.


#### WinBuiltinTerminalServerLicenseServersSid

This value indicates a SID is present in a server that can issue Terminal Server licenses.


#### WinBuiltinUsersSid

This value indicates a SID that matches built-in user accounts. 


#### WinCreatorGroupServerSid

This value indicates a creator group server SID.


#### WinCreatorGroupSid

This value indicates a SID that matches the creator group of an object. This SID is used in inheritable access-control entries.


#### WinCreatorOwnerServerSid

This value indicates a creator owner server SID. 


#### WinCreatorOwnerSid

This value indicates a SID that matches the owner or creator of an object. This SID is used in inheritable access-control entries.


#### WinDialupSid

This value indicates a SID for a dial-up account.


#### WinDigestAuthenticationSid

This value indicates a SID present when the Microsoft Digest authentication package authenticated the client.


#### WinEnterpriseControllersSid

This value indicates a SID for an enterprise controller.


#### WinInteractiveSid

This value indicates a SID for an interactive account. This SID is added to the process of a token when it logs on interactively. The corresponding logon type is LOGON32_LOGON_INTERACTIVE. 


#### WinLocalServiceSid

This value indicates a SID that matches a local service.


#### WinLocalSid

This value indicates a local SID.


#### WinLocalSystemSid

This value indicates a SID that matches the local system.


#### WinLogonIdsSid

This value indicates a SID that matches logon IDs.


#### WinNTLMAuthenticationSid

This value indicates a SID present when the Microsoft NTLM authentication package authenticated the client.


#### WinNetworkServiceSid

This value indicates a SID that matches a network service.


#### WinNetworkSid

This value indicates a SID for a network account. This SID is added to the process of a token when it logs on across a network. The corresponding logon type is LOGON32_LOGON_NETWORK. 


#### WinNtAuthoritySid

This value indicates a SID for the Windows NT authority.


#### WinNullSid

This value indicates a null SID. 


#### WinOtherOrganizationSid

This value indicates a SID present when the user authenticated across a forest with the selective authentication option enabled. If this SID is present, then WinThisOrganizationSid cannot be present.


#### WinProxySid

This value indicates a proxy SID. 


#### WinRemoteLogonIdSid

This value indicates a SID that matches remote logons.


#### WinRestrictedCodeSid

This value indicates a SID for restricted code.


#### WinSChannelAuthenticationSid

This value indicates a SID present when the Secure Channel (SSL/TLS) authentication package authenticated the client.


#### WinSelfSid

This value indicates a SID for self.


#### WinServiceSid

This value indicates a SID for a service. This SID is added to the process of a token when it logs on as a service. The corresponding logon type is LOGON32_LOGON_SERVICE. 


#### WinTerminalServerSid

This value indicates a SID that matches a terminal server account.


#### WinThisOrganizationSid

This value indicates a SID present when the user authenticated from within the forest or across a trust that does not have the selective authentication option enabled. If this SID is present, then WinOtherOrganizationSid cannot be present.


#### WinWorldSid

This value indicates a SID that matches everyone.

`Sid`

A pointer to a buffer that receives the SID structure that corresponds to the <i>SidType</i> parameter. If this parameter is <b>NULL</b>, <i>SidBufferSize</i> must be zero.

`SidBufferSize`

A variable that specifies the size of the <i>Sid</i> buffer in bytes.

`OPTIONAL`

TBD


## Return Value

<b>SecLookupWellKnownSid</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The process ID associated with the currently executing thread does not match the current process ID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size for the <i>Sid</i>, the <i>SidBufferSize</i> parameter, was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
A <b>NULL</b> pointer was passed for <i>Sid</i> parameter or a well-known SID could not be found for the <i>SidType</i> specified. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
This process has terminated so it is not possible to establish a local procedure call (LPC) connection.

</td>
</tr>
</table>

## Remarks

<b>SecLookupWellKnownSid</b> attempts to find a well known SID using a <i>SidType</i> parameter. In addition to looking up well-known SIDs on the local machine, <b>SecLookupWellKnownSid</b> can look up well-known SIDs on the local domain. <b>SecLookupWellKnownSid</b>first checks a list of well-known local SIDs. If the <i>SidType</i> does not correspond to a local well-known SID, the function checks for well-known SIDs on the primary domain. 

If the function cannot find the well known SID for the <i>SidType</i> specified, <b>SecLookupWellKnownSid</b> fails. This can occur if a network time-out prevents the function from finding the SID on the primary domain. It also occurs for a <i>SidType</i> that has no corresponding well-known SID.

<b>SecLookupWellKnownSid</b> is equivalent to the Win32   <b>CreateWellKnownSid</b> function. For user-mode applications, the WELL_KNOWN_SID_TYPE enumeration is defined in <i>winbase.h</i>.

<b>SecLookupWellKnownSid</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupWellKnownSid</b> cannot be used during paging file I/O.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This SecLookupWellKnownSid function is only available starting with Windows Server 2003. This SecLookupWellKnownSid function is only available starting with Windows Server 2003. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | Ksecdd.lib |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-seclookupaccountsid.md">SecLookupAccountSid</a>

<a href="..\ntifs\nf-ntifs-seclookupaccountname.md">SecLookupAccountName</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SecLookupWellKnownSid function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>