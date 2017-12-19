---
UID: NS.NTIFS._SE_TOKEN_USER
title: _SE_TOKEN_USER
author: windows-driver-content
description: The SE_TOKEN_USER structure holds the maximum-sized valid user SID that can be returned by SeQueryInformationToken, GetTokenInformation, or ZwQueryInformationToken with the TokenUser information class. This structure is suitable for stack allocation.
old-location: ifsk\se_token_user.htm
old-project: ifsk
ms.assetid: 3B870461-0C5D-46DF-A850-EB796AE5A4CB
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SE_TOKEN_USER, SE_TOKEN_USER, PSE_TOKEN_USER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SE_TOKEN_USER
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
---

# _SE_TOKEN_USER structure



## -description
The <b>SE_TOKEN_USER</b> structure holds the maximum-sized valid user SID that can be returned by <a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a>, <a href="security.gettokeninformation">GetTokenInformation</a>, or <a href="kernel.zwqueryinformationtoken">ZwQueryInformationToken</a> with the TokenUser information class. This structure is suitable for stack allocation.



## -syntax

````
typedef struct _SE_TOKEN_USER {
  union {
    TOKEN_USER         TokenUser;
    SID_AND_ATTRIBUTES User;
  };
  union {
    SID   Sid;
    UCHAR Buffer[SECURITY_MAX_SID_SIZE];
  };
} SE_TOKEN_USER, *PSE_TOKEN_USER;
````


## -struct-fields

### -field TokenUser

Specifies a <b>TOKEN_USER</b> structure representing the user associated with an access token.


### -field User

Specifies an <b>SID_AND_ATTRIBUTES</b> structure representing the user associated with the access token.


### -field Sid

Specifies a <b>Security Identifier (SID)</b> structure used to uniquely identify users or groups


### -field Buffer

Specifies an array of SECURITY_MAX_SID_SIZE for allocating enough memory for the largest possible SID size.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556742">SID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="ifsk.token_user">TOKEN_USER</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SE_TOKEN_USER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

