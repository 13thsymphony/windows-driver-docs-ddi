---
UID: NF.ntifs.RtlAppendStringToString
title: RtlAppendStringToString function
author: windows-driver-content
description: The RtlAppendStringToString routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.
old-location: ifsk\rtlappendstringtostring.htm
old-project: ifsk
ms.assetid: 8cd94502-c11a-4e6a-87f6-0c6034b6ac09
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RtlAppendStringToString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000, and later versions of all Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlAppendStringToString
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
req.irql: <= APC_LEVEL
---

# RtlAppendStringToString function



## -description
The <b>RtlAppendStringToString</b> routine concatenates two counted strings. It copies bytes from the source up to the length of the destination buffer.



## -syntax

````
NTSTATUS RtlAppendStringToString(
  _Inout_       PSTRING Destination,
  _In_    const STRING  *Source
);
````


## -parameters

### -param Destination [in, out]

A pointer to a counted string to which the string at <i>Source</i> should be appended. 


### -param Source [in]

A pointer to a counted string to be appended to the string at <i>Destination</i>. 


## -returns
The <b>RtlAppendStringToString</b> routine returns STATUS_SUCCESS if it appended the string at <i>Source</i> to the string at <i>Destination</i>. <b>RtlAppendStringToString</b> returns STATUS_BUFFER_TOO_SMALL if the <b>MaximumLength</b> of the <i>Destination</i> string is too small to allow the source string to be appended. 


## -remarks
The sum of the <b>Length</b> members of the <i>Destination</i> and <i>Source</i> strings must be less than or equal to the <b>MaximumLength</b> of the <i>Destination</i> string.

For information about other string-handling routines, see <a href="kernel.strings">Strings</a>. 


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
Version

</th>
<td width="70%">
Available in Microsoft Windows 2000, and later versions of all Windows operating systems.

</td>
</tr>
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
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlappendunicodestringtostring">RtlAppendUnicodeStringToString</a>
</dt>
<dt>
<a href="kernel.rtlappendunicodetostring">RtlAppendUnicodeToString</a>
</dt>
<dt>
<a href="kernel.rtlinitstring">RtlInitString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlAppendStringToString routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

