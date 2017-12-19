---
UID: NF.ntifs.RtlEqualPrefixSid
title: RtlEqualPrefixSid function
author: windows-driver-content
description: The RtlEqualPrefixSid routine determines whether two security-identifier (SID) prefixes are equal. An SID prefix is the entire SID except for the last subauthority value.
old-location: ifsk\rtlequalprefixsid.htm
old-project: ifsk
ms.assetid: 6db96d3b-721f-40d5-8f8d-54cdd33f85c8
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlEqualPrefixSid
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
req.alt-api: RtlEqualPrefixSid
req.alt-loc: Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntdll.lib
req.dll: Ntdll.dll
req.irql: <= APC_LEVEL
---

# RtlEqualPrefixSid function



## -description
The <b>RtlEqualPrefixSid</b> routine determines whether two security-identifier (SID) prefixes are equal. An SID prefix is the entire SID except for the last subauthority value. 



## -syntax

````
BOOLEAN RtlEqualPrefixSid(
  _In_ PSID Sid1,
  _In_ PSID Sid2
);
````


## -parameters

### -param Sid1 [in]

Pointer to the first SID structure to compare. Must point to a valid SID. 


### -param Sid2 [in]

Pointer to the second SID structure to compare. Must point to a valid SID. 


## -returns
<b>RtlEqualPrefixSid</b> returns <b>TRUE</b> if the SID prefixes are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined. 


## -remarks
<b>RtlEqualPrefixSid</b> enables a server in one domain to verify an attempt by a user to log on to another domain. For example, if a user attempts to log on to RemoteDomain from a workstation in LocalDomain, the server for LocalDomain can request the SIDs for the user and the user's groups from RemoteDomain. The domain controller for RemoteDomain responds with the relevant SIDs. 

All SIDs for a specified domain necessarily have the same prefix. When the server receives the user's SIDs, it can call <b>RtlEqualPrefixSid</b> for each SID, comparing the user or group SID against the SID for RemoteDomain. If any of the SID prefixes are not equal, the server refuses the logon attempt. 

It is advisable to modify the SID for a domain before comparing it with a group or user SID. If the SID for RemoteDomain is S-1-1234-8, each group or user SID for that domain will have S-1-1234-8 as its prefix. To compare the SIDs by using <b>RtlEqualPrefixSid</b>, the caller copies the domain SID and adds any subauthority relative identifier value to the copy, thereby creating an SID in the form S-1-1234-8-0. (The relative identifier, or RID, is the portion of a SID that identifies a user or group in relation to the authority that issued the SID.) The caller then uses the modified domain SID as a template against which the group and user SIDs are compared. 

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.


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
<dt>Ntdll.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Ntdll.dll</dt>
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
<a href="ifsk.rtlcopysid">RtlCopySid</a>
</dt>
<dt>
<a href="ifsk.rtlequalsid">RtlEqualSid</a>
</dt>
<dt>
<a href="ifsk.rtlvalidsid">RtlValidSid</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEqualPrefixSid routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

