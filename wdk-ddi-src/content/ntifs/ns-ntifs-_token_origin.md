---
UID: NS:ntifs._TOKEN_ORIGIN
title: _TOKEN_ORIGIN
author: windows-driver-content
description: The TOKEN_ORIGIN structure contains information about the origin of the logon session.
old-location: ifsk\token_origin.htm
old-project: ifsk
ms.assetid: 6e2175f3-3d63-40d0-854b-440862530aa8
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _TOKEN_ORIGIN, TOKEN_ORIGIN, *PTOKEN_ORIGIN
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_ORIGIN
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
req.irql: 
req.typenames: TOKEN_ORIGIN, *PTOKEN_ORIGIN
---

# _TOKEN_ORIGIN structure



## -description
The TOKEN_ORIGIN structure contains information about the origin of the logon session. 



## -syntax

````
typedef struct _TOKEN_ORIGIN {
  LUID OriginatingLogonSession;
} TOKEN_ORIGIN, *PTOKEN_ORIGIN;
````


## -struct-fields

### -field OriginatingLogonSession

The locally unique identifier (LUID) for the logon session. If the token resulted from a logon using explicit credentials, such as passing name, domain, and password to the user-mode <b>LogonUser</b> function, then this member will contain the ID of the logon session that created it. If the token resulted from network authentication, such as a call to the user-mode <b>AcceptSecurityContext</b>, or a call to the user-mode <b>LogonUser</b> function with dwLogonType set to LOGON32_LOGON_NETWORK or LOGON32_LOGON_NETWORK_CLEARTEXT, then this member will be zero. 


## -remarks
The TOKEN_ORIGIN structure is available on Windows Server 2003 or later.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h or FltKernel.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm-_acl.md">ACL</a>
</dt>
<dt>
<a href="..\wudfddi\ne-wudfddi-_security_impersonation_level.md">SECURITY_IMPERSONATION_LEVEL</a>
</dt>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_luid_and_attributes.md">LUID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sefiltertoken.md">SeFilterToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-sequeryinformationtoken.md">SeQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-setokenisrestricted.md">SeTokenIsRestricted</a>
</dt>
<dt>
<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>
</dt>
<dt>
<a href="..\ntifs\ne-ntifs-_token_information_class.md">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwqueryinformationtoken.md">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-zwsetinformationtoken.md">ZwSetInformationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_ORIGIN structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

