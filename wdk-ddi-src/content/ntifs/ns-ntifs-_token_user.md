---
UID: NS.NTIFS._TOKEN_USER
title: _TOKEN_USER
author: windows-driver-content
description: TOKEN_USER identifies the user associated with an access token.
old-location: ifsk\token_user.htm
old-project: ifsk
ms.assetid: 0168f1ea-d2b0-4343-b6e7-c6cc97214201
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _TOKEN_USER, TOKEN_USER, *PTOKEN_USER, PTOKEN_USER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: TOKEN_USER
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

# _TOKEN_USER structure



## -description
TOKEN_USER identifies the user associated with an access token. 



## -syntax

````
typedef struct _TOKEN_USER {
  SID_AND_ATTRIBUTES User;
} TOKEN_USER, *PTOKEN_USER;
````


## -struct-fields

### -field User

Specifies an SID_AND_ATTRIBUTES structure representing the user associated with the access token. 


## -remarks
Unlike TOKEN_GROUPS structures, TOKEN_USER structures cannot be passed to <b>SeFilterToken</b>. Nevertheless, it is possible to designate a user SID as a deny-only SID by specifying the user SID as one of the group SIDs in the TOKEN_GROUPS structure passed to <b>SeFilterToken</b>. 


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
<a href="ifsk.sefiltertoken">SeFilterToken</a>
</dt>
<dt>
<a href="ifsk.sequeryinformationtoken">SeQueryInformationToken</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
<dt>
<a href="ifsk.sid_and_attributes">SID_AND_ATTRIBUTES</a>
</dt>
<dt>
<a href="ifsk.token_groups">TOKEN_GROUPS</a>
</dt>
<dt>
<a href="ifsk.token_information_class">TOKEN_INFORMATION_CLASS</a>
</dt>
<dt>
<a href="kernel.zwqueryinformationtoken">ZwQueryInformationToken</a>
</dt>
<dt>
<a href="kernel.zwsetinformationtoken">ZwSetInformationToken</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20TOKEN_USER structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

