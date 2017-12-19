---
UID: NF.ntifs.RtlEqualSid
title: RtlEqualSid function
author: windows-driver-content
description: The RtlEqualSid routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.
old-location: ifsk\rtlequalsid.htm
old-project: ifsk
ms.assetid: 4976fc27-c28a-46ec-ac07-19505cda8f14
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlEqualSid
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
req.alt-api: RtlEqualSid
req.alt-loc: NtosKrnl.exe,Ntdll.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any
---

# RtlEqualSid function



## -description
The <b>RtlEqualSid</b> routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal. 



## -syntax

````
BOOLEAN RtlEqualSid(
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
<b>RtlEqualSid</b> returns <b>TRUE</b> if the SID structures are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined. 


## -remarks
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
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe (kernel mode); </dt>
<dt>Ntdll.dll (user mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
Any

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.rtlcopysid">RtlCopySid</a>
</dt>
<dt>
<a href="ifsk.rtlequalprefixsid">RtlEqualPrefixSid</a>
</dt>
<dt>
<a href="ifsk.rtlvalidsid">RtlValidSid</a>
</dt>
<dt>
<a href="ifsk.sid">SID</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEqualSid routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
