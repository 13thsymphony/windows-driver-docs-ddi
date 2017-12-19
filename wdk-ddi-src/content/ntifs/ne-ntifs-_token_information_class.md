---
UID: NE.ntifs._TOKEN_INFORMATION_CLASS
title: _TOKEN_INFORMATION_CLASS
author: windows-driver-content
description: The TOKEN_INFORMATION_CLASS enumeration type contains values that specify the type of information being assigned to or retrieved from an access token.
old-location: ifsk\token_information_class.htm
old-project: ifsk
ms.assetid: dd2323fa-2c58-462e-905f-3b201ef0c343
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _TOKEN_INFORMATION_CLASS, *PTOKEN_INFORMATION_CLASS, TOKEN_INFORMATION_CLASS, PTOKEN_INFORMATION_CLASS
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
req.alt-api: TOKEN_INFORMATION_CLASS
req.alt-loc: ntifs.h
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
---

# _TOKEN_INFORMATION_CLASS enumeration



## -description
The <b>TOKEN_INFORMATION_CLASS</b> enumeration type contains values that specify the type of information being assigned to or retrieved from an access token. 


<a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a> and <a href="kernel.zwqueryinformationtoken">ZwQueryInformationToken</a> use <b>TOKEN_INFORMATION_CLASS</b> values to indicate the type of token information to retrieve. 



## -syntax

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


## -enum-fields

### -field TokenUser

The buffer receives a <a href="ifsk.token_user">TOKEN_USER</a> structure containing the token's user account. 


### -field TokenGroups

The buffer receives a <a href="ifsk.token_groups">TOKEN_GROUPS</a> structure containing the group accounts associated with the token. 


### -field TokenPrivileges

The buffer receives a <a href="ifsk.token_privileges">TOKEN_PRIVILEGES</a> structure containing the token's privileges. 


### -field TokenOwner

The buffer receives a <a href="ifsk.token_owner">TOKEN_OWNER</a> structure containing the default owner SID for newly created objects. 


### -field TokenPrimaryGroup

The buffer receives a <a href="ifsk.token_primary_group">TOKEN_PRIMARY_GROUP</a> structure containing the default primary group SID for newly created objects. 


### -field TokenDefaultDacl

The buffer receives a <a href="ifsk.token_default_dacl">TOKEN_DEFAULT_DACL</a> structure containing the default discretionary ACL (DACL)) for newly created objects. 


### -field TokenSource

The buffer receives a <a href="ifsk.token_source">TOKEN_SOURCE</a> structure containing the source of the token. TOKEN_QUERY_SOURCE access is needed to retrieve this information. 


### -field TokenType

The buffer receives a <a href="ifsk.token_type">TOKEN_TYPE</a> value indicating whether the token is a primary or impersonation token. 


### -field TokenImpersonationLevel

The buffer receives a <a href="ifsk.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a> value indicating the impersonation level of the token. If the access token is not an impersonation token, the call to <a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a> or <a href="kernel.zwqueryinformationtoken">ZwQueryInformationToken</a> fails. 


### -field TokenStatistics

The buffer receives a <a href="ifsk.token_statistics">TOKEN_STATISTICS</a> structure containing various token statistics. 


### -field TokenRestrictedSids

The buffer receives a <a href="ifsk.token_groups">TOKEN_GROUPS</a> structure containing the list of restricting SIDs in a restricted token. This value is valid starting with Windows Vista.


### -field TokenSessionId

The buffer receives a DWORD value that indicates the Terminal Services session identifier associated with the token. If the token is associated with the Terminal Server console session, the session identifier is zero. A nonzero session identifier indicates a Terminal Services client session. In a non-Terminal Services environment, the session identifier is zero. This value is valid starting with Windows Vista.


### -field TokenGroupsAndPrivileges

The buffer receives a <a href="ifsk.token_groups_and_privileges">TOKEN_GROUPS_AND_PRIVILEGES</a> structure that contains the user SID, the group accounts, the restricted SIDs, and the authentication ID associated with the token. This value is valid starting with Windows Vista.


### -field TokenSessionReference

Reserved for system use.


### -field TokenSandBoxInert

The buffer receives a DWORD value that is nonzero if the token includes the SANDBOX_INERT flag. This value is valid starting with Windows Vista.


### -field TokenAuditPolicy

Reserved for system use.


### -field TokenOrigin

The buffer receives a <a href="ifsk.token_origin">TOKEN_ORIGIN</a> value. 

If the token resulted from a logon that used explicit credentials, such as passing a name, domain, and password to the user-mode <a href="security.logonuser">LogonUser</a> function, then the <b>TOKEN_ORIGIN</b> structure will contain the ID of the logon session that created it.

If the token resulted from network authentication, such as a call to user-mode <b>AcceptSecurityContext</b> function or a call to user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this value will be zero.

 This value is valid starting with Windows Server 2003.


### -field TokenLinkedToken

The buffer receives a <a href="security.token_linked_token">TOKEN_LINKED_TOKEN</a> structure that contains a handle to another token that is linked to this token. This value is valid starting with Windows Vista.


### -field TokenElevation

The buffer receives a <a href="security.token_elevation">TOKEN_ELEVATION</a> structure that specifies whether the token is elevated. This value is valid starting with Windows Vista.


### -field TokenHasRestrictions

The buffer receives a <b>DWORD</b> value that is nonzero if the token has ever been filtered. This value is valid starting with Windows Vista.


### -field TokenAccessInformation

The buffer receives a <a href="security.token_access_information">TOKEN_ACCESS_INFORMATION</a> structure that specifies  security information contained in the token. This value is valid starting with Windows Vista.


### -field TokenVirtualizationAllowed

The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="security.v_gly#_security_virtualization_gly#_security_virtualization_gly"><i>virtualization</i></a> is allowed for the token. This value is valid starting with Windows Vista.


### -field TokenVirtualizationEnabled

The buffer receives a <b>DWORD</b> value that is nonzero if  <a href="security.v_gly#_security_virtualization_gly#_security_virtualization_gly"><i>virtualization</i></a> is enabled for the token. This value is valid starting with Windows Vista.


### -field TokenIntegrityLevel

The buffer receives a <a href="security.token_mandatory_label">TOKEN_MANDATORY_LABEL</a> structure that specifies the token's integrity level. This value is valid starting with Windows Vista. For <a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a> the output is the actual integrity level  (<b>DWORD</b>).


### -field TokenUIAccess

The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the UIAccess flag set. This value is valid starting with Windows Vista.


### -field TokenMandatoryPolicy

The buffer receives a <a href="security.token_mandatory_policy">TOKEN_MANDATORY_POLICY</a> structure that specifies the token's mandatory integrity policy. This value is valid starting with Windows Vista.


### -field TokenLogonSid

The buffer receives a <a href="ifsk.token_groups">TOKEN_GROUPS</a> structure that specifies the token's logon SID. This value is valid starting with Windows Vista.


### -field TokenIsAppContainer

The buffer receives a <b>DWORD</b> value that is nonzero if  the token has the application container flag set. This value is valid starting with Windows 8.


### -field TokenCapabilities

The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each token capability. This value is valid starting with Windows 8.


### -field TokenAppContainerSid

The buffer receives a <b>TOKEN_APPCONTAINER_INFORMATION</b> structure that contains the AppContainerSid associated with the token. If the token is not associated with an app container, the TokenAppContainer member of the <b>TOKEN_APPCONTAINER_INFORMATION</b> structure points to NULL. This value is valid starting with Windows 8.


### -field TokenAppContainerNumber

The buffer receives a <b>DWORD</b> value that is the application container number. This value is valid starting with Windows 8.


### -field TokenUserClaimAttributes

The buffer receives a <a href="security.token_mandatory_policy">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the user's claim attributes. This value is valid starting with Windows 8.


### -field TokenDeviceClaimAttributes

The buffer receives a <a href="security.token_mandatory_policy">CLAIM_SECURITY_ATTRIBUTES_INFORMATION</a> structure that specifies the device's claim attributes. This value is valid starting with Windows 8.


### -field TokenRestrictedUserClaimAttributes

Reserved for system use. 


### -field TokenRestrictedDeviceClaimAttributes

Reserved for system use. 


### -field TokenDeviceGroups

The buffer receives a <b>TOKEN_GROUPS</b> structure and an array of <b>SID_AND_ATTRIBUTES</b> structures for each device group. This value is valid starting with Windows 8.


### -field TokenRestrictedDeviceGroups

Reserved for system use. 


### -field TokenSecurityAttributes

Reserved for system use. 


### -field TokenIsRestricted

Reserved for system use. 


### -field TokenProcessTrustLevel

Reserved for system use. 


### -field MaxTokenInfoClass

The maximum value for this enumeration.


## -remarks


## -requirements
<table>
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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.acl">ACL</a>
</dt>
<dt>
<a href="ifsk.security_impersonation_level">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
<dt>
<a href="ifsk.sefiltertoken">SeFilterToken</a>
</dt>
<dt>
<a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a>
</dt>
<dt>
<a href="ifsk.setokenisrestricted">SeTokenIsRestricted</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="ifsk.token_default_dacl">TOKEN_DEFAULT_DACL</a>
</dt>
<dt>
<a href="ifsk.token_groups">TOKEN_GROUPS</a>
</dt>
<dt>
<a href="ifsk.token_owner">TOKEN_OWNER</a>
</dt>
<dt>
<a href="ifsk.token_origin">TOKEN_ORIGIN</a>
</dt>
<dt>
<a href="ifsk.token_primary_group">TOKEN_PRIMARY_GROUP</a>
</dt>
<dt>
<a href="ifsk.token_privileges">TOKEN_PRIVILEGES</a>
</dt>
<dt>
<a href="ifsk.token_source">TOKEN_SOURCE</a>
</dt>
<dt>
<a href="ifsk.token_statistics">TOKEN_STATISTICS</a>
</dt>
<dt>
<a href="ifsk.token_type">TOKEN_TYPE</a>
</dt>
<dt>
<a href="ifsk.token_user">TOKEN_USER</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationtoken">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="kernel.zwsetinformationtoken">ZwSetInformationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_INFORMATION_CLASS enumeration%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

