---
UID: NF.wdm.RtlCompareUnicodeString
title: RtlCompareUnicodeString
author: windows-driver-content
description: The RtlCompareUnicodeString routine compares two Unicode strings.
old-location: kernel\rtlcompareunicodestring.htm
old-project: kernel
ms.assetid: 82567434-be54-4436-a26e-9a89a532addf
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RtlCompareUnicodeString
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
req.alt-api: RtlCompareUnicodeString
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
req.irql: PASSIVE_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# RtlCompareUnicodeString function



## -description
<p>The <b>RtlCompareUnicodeString</b> routine compares two Unicode strings.</p>


## -syntax

````
LONG RtlCompareUnicodeString(
  _In_ PCUNICODE_STRING String1,
  _In_ PCUNICODE_STRING String2,
  _In_ BOOLEAN          CaseInSensitive
);
````


## -parameters
<dl>

### -param String1 [in]

<dd>
<p>Pointer to the first string.</p>
</dd>

### -param String2 [in]

<dd>
<p>Pointer to the second string.</p>
</dd>

### -param CaseInSensitive [in]

<dd>
<p>If <b>TRUE</b>, case should be ignored when doing the comparison. </p>
</dd>
</dl>

## -returns
<p><b>RtlCompareUnicodeString</b> returns a signed value that gives the results of the comparison:</p><dl>
<dt><b>Zero</b></dt>
</dl><p><i>String1</i> equals <i>String2</i>.</p><dl>
<dt><b>&lt; Zero</b></dt>
</dl><p><i>String1</i> is less than <i>String2</i>.</p><dl>
<dt><b>&gt; Zero </b></dt>
</dl><p><i>String1</i> is greater than <i>String2</i>.</p>

<p> </p>

## -remarks


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
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddk\nf-ntddk-rtlcomparestring.md">RtlCompareString</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-rtlequalstring.md">RtlEqualString</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCompareUnicodeString routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
