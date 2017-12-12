---
UID: NF.wdm.RtlInitUnicodeString
title: RtlInitUnicodeString function
author: windows-driver-content
description: For more information, see the WdmlibRtlInitUnicodeStringEx function.
old-location: kernel\rtlinitunicodestring.htm
old-project: kernel
ms.assetid: c6ef7438-36a6-4da6-b745-2985d9b30614
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: RtlInitUnicodeString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlInitUnicodeString
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
req.irql: For more information, see  the Remarks section of the WdmlibRtlInitUnicodeStringEx  function.
req.product: Windows 10 or later.
---

# RtlInitUnicodeString function



## -description
For more information, see  the <a href="kernel.wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.



## -syntax

````
VOID RtlInitUnicodeString(
  _Out_    PUNICODE_STRING DestinationString,
  _In_opt_ PCWSTR          SourceString
);
````


## -parameters

### -param DestinationString [out]

For more information, see  the <a href="kernel.wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


### -param SourceString [in, optional]

For more information, see  the <a href="kernel.wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


## -returns
For more information, see  the <a href="kernel.wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a> function.


## -remarks
The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




Pointer to a null-terminated string to initialize the counted string with.

<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="kernel.rtlinitansistring">RtlInitAnsiString</a>, <a href="kernel.rtlinitstring">RtlInitString</a>, and <b>RtlInitUnicodeString</b> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.


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
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
For more information, see  the Remarks section of the WdmlibRtlInitUnicodeStringEx  function.

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlunicodestringinit">RtlUnicodeStringInit</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringinitex">RtlUnicodeStringInitEx</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
<dt>
<a href="kernel.wdmlibrtlinitunicodestringex">WdmlibRtlInitUnicodeStringEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlInitUnicodeString routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

