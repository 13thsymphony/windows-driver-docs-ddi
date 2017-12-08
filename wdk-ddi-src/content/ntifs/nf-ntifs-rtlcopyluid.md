---
UID: NF.ntifs.RtlCopyLuid
title: RtlCopyLuid function
author: windows-driver-content
description: The RtlCopyLuid routine copies a locally unique identifier (LUID) to a buffer.
old-location: ifsk\rtlcopyluid.htm
old-project: ifsk
ms.assetid: ebda25f4-77d6-4178-9ff8-b1f0e95df9f0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlCopyLuid
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
req.alt-api: RtlCopyLuid
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: < DISPATCH_LEVEL
---

# RtlCopyLuid function



## -description
The <b>RtlCopyLuid</b> routine copies a locally unique identifier (LUID) to a buffer. 


## -syntax

````
VOID RtlCopyLuid(
  _Out_ PLUID DestinationLuid,
  _In_  PLUID SourceLuid
);
````


## -parameters

### -param DestinationLuid [out]

Pointer to a caller-allocated buffer to receive a copy of the source LUID structure. The buffer must be at least <b>sizeof(</b>LUID<b>)</b>.

### -param SourceLuid [in]

Pointer to the source LUID structure to be copied. 

## -returns
None

## -remarks
<b>RtlCopyLuid</b> does not check whether the LUID at <i>SourceLuid</i> is structurally valid. 

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
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.luid">LUID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>
</dt>
<dt>
<a href="ifsk.sequeryauthenticationidtoken">SeQueryAuthenticationIdToken</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCopyLuid routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
