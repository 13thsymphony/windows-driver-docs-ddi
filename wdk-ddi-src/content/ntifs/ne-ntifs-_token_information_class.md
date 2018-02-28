---
UID: NE:ntifs._TOKEN_INFORMATION_CLASS
title: "_TOKEN_INFORMATION_CLASS"
author: windows-driver-content
description: The TOKEN_INFORMATION_CLASS enumeration type contains values that specify the type of information being assigned to or retrieved from an access token.
old-location: ifsk\token_information_class.htm
old-project: ifsk
ms.assetid: dd2323fa-2c58-462e-905f-3b201ef0c343
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PTOKEN_INFORMATION_CLASS, MaxTokenInfoClass, PTOKEN_INFORMATION_CLASS, PTOKEN_INFORMATION_CLASS enumeration pointer [Installable File System Drivers], TOKEN_INFORMATION_CLASS, TOKEN_INFORMATION_CLASS enumeration [Installable File System Drivers], TokenAccessInformation, TokenAppContainerNumber, TokenAppContainerSid, TokenAuditPolicy, TokenCapabilities, TokenDefaultDacl, TokenDeviceClaimAttributes, TokenDeviceGroups, TokenElevation, TokenGroups, TokenGroupsAndPrivileges, TokenHasRestrictions, TokenImpersonationLevel, TokenIntegrityLevel, TokenIsAppContainer, TokenIsRestricted, TokenLinkedToken, TokenLogonSid, TokenMandatoryPolicy, TokenOrigin, TokenOwner, TokenPrimaryGroup, TokenPrivileges, TokenProcessTrustLevel, TokenRestrictedDeviceClaimAttributes, TokenRestrictedDeviceGroups, TokenRestrictedSids, TokenRestrictedUserClaimAttributes, TokenSandBoxInert, TokenSecurityAttributes, TokenSessionId, TokenSessionReference, TokenSource, TokenStatistics, TokenType, TokenUIAccess, TokenUser, TokenUserClaimAttributes, TokenVirtualizationAllowed, TokenVirtualizationEnabled, _TOKEN_INFORMATION_CLASS, ifsk.token_information_class, ntifs/MaxTokenInfoClass, ntifs/PTOKEN_INFORMATION_CLASS, ntifs/TOKEN_INFORMATION_CLASS, ntifs/TokenAccessInformation, ntifs/TokenAppContainerNumber, ntifs/TokenAppContainerSid, ntifs/TokenAuditPolicy, ntifs/TokenCapabilities, ntifs/TokenDefaultDacl, ntifs/TokenDeviceClaimAttributes, ntifs/TokenDeviceGroups, ntifs/TokenElevation, ntifs/TokenGroups, ntifs/TokenGroupsAndPrivileges, ntifs/TokenHasRestrictions, ntifs/TokenImpersonationLevel, ntifs/TokenIntegrityLevel, ntifs/TokenIsAppContainer, ntifs/TokenIsRestricted, ntifs/TokenLinkedToken, ntifs/TokenLogonSid, ntifs/TokenMandatoryPolicy, ntifs/TokenOrigin, ntifs/TokenOwner, ntifs/TokenPrimaryGroup, ntifs/TokenPrivileges, ntifs/TokenProcessTrustLevel, ntifs/TokenRestrictedDeviceClaimAttributes, ntifs/TokenRestrictedDeviceGroups, ntifs/TokenRestrictedSids, ntifs/TokenRestrictedUserClaimAttributes, ntifs/TokenSandBoxInert, ntifs/TokenSecurityAttributes, ntifs/TokenSessionId, ntifs/TokenSessionReference, ntifs/TokenSource, ntifs/TokenStatistics, ntifs/TokenType, ntifs/TokenUIAccess, ntifs/TokenUser, ntifs/TokenUserClaimAttributes, ntifs/TokenVirtualizationAllowed, ntifs/TokenVirtualizationEnabled, securitystructures_525fb6c8-0030-40ea-927a-72fe89eff87e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntifs.h
api_name:
-	TOKEN_INFORMATION_CLASS
product: Windows
targetos: Windows
req.typenames: TOKEN_INFORMATION_CLASS, *PTOKEN_INFORMATION_CLASS
---

# _TOKEN_INFORMATION_CLASS Enumeration
The <b>TOKEN_INFORMATION_CLASS</b> enumeration type contains values that specify the type of information being assigned to or retrieved from an access token. 


<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> and <a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a> use <b>TOKEN_INFORMATION_CLASS</b> values to indicate the type of token information to retrieve.

## Syntax
````
typedef enum _TOKEN_INFORMATION_CLASS { 
  TokenUser                             = 1,
  TokenGroups                           = 2,
  TokenPrivileges                       = 3,
  TokenOwner                            = 4,
  TokenPrimaryGroup                     = 5,
  TokenDefaultDacl                      = 6,
  TokenSource                           = 7,
  TokenType                             = 8,
  TokenImpersonationLevel               = 9,
  TokenStatistics                       = 10,
  TokenRestrictedSids                   = 11,
  TokenSessionId                        = 12,
  TokenGroupsAndPrivileges              = 13,
  TokenSessionReference                 = 14,
  TokenSandBoxInert                     = 15,
  TokenAuditPolicy                      = 16,
  TokenOrigin                           = 17,
  TokenLinkedToken                      = 19,
  TokenElevation                        = 20,
  TokenHasRestrictions                  = 21,
  TokenAccessInformation                = 22,
  TokenVirtualizationAllowed            = 23,
  TokenVirtualizationEnabled            = 24,
  TokenIntegrityLevel                   = 25,
  TokenUIAccess                         = 26,
  TokenMandatoryPolicy                  = 27,
  TokenLogonSid                         = 28,
  TokenIsAppContainer                   = 29,
  TokenCapabilities                     = 30,
  TokenAppContainerSid                  = 31,
  TokenAppContainerNumber               = 32,
  TokenUserClaimAttributes              = 33,
  TokenDeviceClaimAttributes            = 34,
  TokenRestrictedUserClaimAttributes    = 35,
  TokenRestrictedDeviceClaimAttributes  = 36,
  TokenDeviceGroups                     = 37,
  TokenRestrictedDeviceGroups           = 38,
  TokenSecurityAttributes               = 39,
  TokenIsRestricted                     = 40,
  TokenProcessTrustLevel                = 41,
  MaxTokenInfoClass                     = 42
} TOKEN_INFORMATION_CLASS, *PTOKEN_INFORMATION_CLASS;
````

## Constants

<table>
            
                <tr>
                    <td>MaxTokenInfoClass</td>
                    <td>The maximum value for this enumeration.</td>
                </tr>
            
                <tr>
                    <td>TokenAccessInformation</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/cb727b91-c88f-48f3-8329-020d3f727dc7">TOKEN_ACCESS_INFORMATION</a> structure that specifies  security information contained in the token. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenAppContainerNumber</td>
                    <td>The buffer receives a <b>DWORD</b> value that is the application container number. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenAppContainerSid</td>
                    <td>The buffer receives a <b>TOKEN_APPCONTAINER_INFORMATION</b> structure that contains the AppContainerSid associated with the token. If the token is not associated with an app container, the TokenAppContainer member of the <b>TOKEN_APPCONTAINER_INFORMATION</b> structure points to NULL. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenAuditPolicy</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenBnoIsolation</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>TokenCapabilities</td>
                    <td>The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each token capability. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenChildProcessFlags</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>TokenDefaultDacl</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a> structure containing the default discretionary ACL (DACL)) for newly created objects.</td>
                </tr>
            
                <tr>
                    <td>TokenDeviceClaimAttributes</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/f5fc438b-c4f0-46f6-a188-52ce660d13da">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the device's claim attributes. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenDeviceGroups</td>
                    <td>The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each device group. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenElevation</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/a1c87818-f092-43cf-872d-4bb2590a944b">TOKEN_ELEVATION</a> structure that specifies whether the token is elevated. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenElevationType</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>TokenGroups</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a> structure containing the group accounts associated with the token.</td>
                </tr>
            
                <tr>
                    <td>TokenGroupsAndPrivileges</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_groups_and_privileges.md">TOKEN_GROUPS_AND_PRIVILEGES</a> structure that contains the user SID, the group accounts, the restricted SIDs, and the authentication ID associated with the token. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenHasRestrictions</td>
                    <td>The buffer receives a <b>DWORD</b> value that is nonzero if the token has ever been filtered. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenImpersonationLevel</td>
                    <td>The buffer receives a <a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a> value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> or <a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a> fails.</td>
                </tr>
            
                <tr>
                    <td>TokenIntegrityLevel</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/cf37eb34-ee90-43c6-97a9-c5edfcba2bc5">TOKEN_MANDATORY_LABEL</a> structure that specifies the token's integrity level. This value is valid starting with Windows Vista. For <a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a> the output is the actual integrity level  (<b>DWORD</b>).</td>
                </tr>
            
                <tr>
                    <td>TokenIsAppContainer</td>
                    <td>The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the application container flag set. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenIsRestricted</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenLinkedToken</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/a77dd410-1074-4196-8323-ccf52ed0375a">TOKEN_LINKED_TOKEN</a> structure that contains a handle to another token that is linked to this token. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenLogonSid</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a> structure that specifies the token's logon SID. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenMandatoryPolicy</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/f5fc438b-c4f0-46f6-a188-52ce660d13da">TOKEN_MANDATORY_POLICY</a> structure that specifies the token's mandatory integrity policy. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenOrigin</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_origin.md">TOKEN_ORIGIN</a> value. 

If the token resulted from a logon that used explicit credentials, such as passing a name, domain, and password to the user-mode <a href="https://msdn.microsoft.com/a6d880a0-0aed-4bdb-89c9-4f667ecb510e">LogonUser</a> function, then the <b>TOKEN_ORIGIN</b> structure will contain the ID of the logon session that created it.

If the token resulted from network authentication, such as a call to user-mode <b>AcceptSecurityContext</b> function or a call to user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this value will be zero.

 This value is valid starting with Windows Server 2003.</td>
                </tr>
            
                <tr>
                    <td>TokenOwner</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a> structure containing the default owner SID for newly created objects.</td>
                </tr>
            
                <tr>
                    <td>TokenPrimaryGroup</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a> structure containing the default primary group SID for newly created objects.</td>
                </tr>
            
                <tr>
                    <td>TokenPrivateNameSpace</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>TokenPrivileges</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a> structure containing the token's privileges.</td>
                </tr>
            
                <tr>
                    <td>TokenProcessTrustLevel</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenRestrictedDeviceClaimAttributes</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenRestrictedDeviceGroups</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenRestrictedSids</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a> structure containing the list of restricting SIDs in a restricted token. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenRestrictedUserClaimAttributes</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenSandBoxInert</td>
                    <td>The buffer receives a DWORD value that is nonzero if the token includes the SANDBOX_INERT flag. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenSecurityAttributes</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenSessionId</td>
                    <td>The buffer receives a DWORD value that indicates the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenSessionReference</td>
                    <td>Reserved for system use.</td>
                </tr>
            
                <tr>
                    <td>TokenSingletonAttributes</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>TokenSource</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a> structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information.</td>
                </tr>
            
                <tr>
                    <td>TokenStatistics</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a> structure containing various token statistics.</td>
                </tr>
            
                <tr>
                    <td>TokenType</td>
                    <td>The buffer receives a <a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a> value indicating whether the token is a primary or impersonation token.</td>
                </tr>
            
                <tr>
                    <td>TokenUIAccess</td>
                    <td>The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the UIAccess flag set. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenUser</td>
                    <td>The buffer receives a <a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a> structure containing the token's user account.</td>
                </tr>
            
                <tr>
                    <td>TokenUserClaimAttributes</td>
                    <td>The buffer receives a <a href="https://msdn.microsoft.com/f5fc438b-c4f0-46f6-a188-52ce660d13da">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the user's claim attributes. This value is valid starting with Windows 8.</td>
                </tr>
            
                <tr>
                    <td>TokenVirtualizationAllowed</td>
                    <td>The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="https://msdn.microsoft.com/library/windows/hardware/dn614617">virtualization</a> is allowed for the token. This value is valid starting with Windows Vista.</td>
                </tr>
            
                <tr>
                    <td>TokenVirtualizationEnabled</td>
                    <td>The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="https://msdn.microsoft.com/library/windows/hardware/dn614617">virtualization</a> is enabled for the token. This value is valid starting with Windows Vista.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntifs.h (include Ntifs.h) |

## See Also

<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>



<a href="..\ntifs\ns-ntifs-_token_source.md">TOKEN_SOURCE</a>



<a href="..\wdm\ns-wdm-_acl.md">ACL</a>



<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>



<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>



<a href="..\ntifs\ns-ntifs-_token_privileges.md">TOKEN_PRIVILEGES</a>



<a href="..\ntifs\ns-ntifs-_token_origin.md">TOKEN_ORIGIN</a>



<a href="..\ntifs\ns-ntifs-_token_groups.md">TOKEN_GROUPS</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\ns-ntifs-_token_user.md">TOKEN_USER</a>



<a href="..\ntifs\ns-ntifs-_token_statistics.md">TOKEN_STATISTICS</a>



<a href="..\ntifs\ns-ntifs-_token_default_dacl.md">TOKEN_DEFAULT_DACL</a>



<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>



<a href="..\ntifs\ne-ntifs-_token_type.md">TOKEN_TYPE</a>



<a href="..\ntifs\ns-ntifs-_token_owner.md">TOKEN_OWNER</a>



<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>



<a href="..\ntifs\ns-ntifs-_token_primary_group.md">TOKEN_PRIMARY_GROUP</a>



<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_INFORMATION_CLASS enumeration%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>