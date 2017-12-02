---
UID: NF.ntddk.RtlUpperString
title: RtlUpperString
author: windows-driver-content
description: The RtlUpperString routine copies the given SourceString to the DestinationString buffer, converting it to uppercase.
old-location: kernel\rtlupperstring.htm
old-project: kernel
ms.assetid: 3a120831-deac-4075-9aa7-8ae39ac29363
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlUpperString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUpperString
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
req.irql: <=APC_LEVEL
req.iface: 
---

# RtlUpperString function



## -description
<p>The <b>RtlUpperString</b> routine copies the given <i>SourceString</i> to the <i>DestinationString</i> buffer, converting it to uppercase.</p>


## -syntax

````
VOID RtlUpperString(
  _Inout_       PSTRING DestinationString,
  _In_    const STRING  *SourceString
);
````


## -parameters
<dl>

### -param DestinationString [in, out]

<dd>
<p>Pointer to the buffer for the converted destination string. </p>
</dd>

### -param SourceString [in]

<dd>
<p>Pointer to the source string to be converted to uppercase. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The <b>MaximumLength</b> and <b>Buffer</b> members of <i>DestinationString</i> are not modified by this routine.</p>

<p>The number of bytes copied from <i>SourceString</i> is either the <b>Length</b> of <i>SourceString</i> or the <b>MaximumLength</b> of <i>DestinationString</i>, whichever is smaller. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlupperchar.md">RtlUpperChar</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUpperString routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
