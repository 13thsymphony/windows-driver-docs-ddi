---
UID: NF.ntstrsafe.RtlUnicodeStringValidateEx
title: RtlUnicodeStringValidateEx function
author: windows-driver-content
description: The RtlUnicodeStringValidateEx function validates the contents of a UNICODE_STRING structure.
old-location: kernel\rtlunicodestringvalidateex.htm
old-project: kernel
ms.assetid: 864935c4-28b8-4738-ac83-e51e6988248b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RtlUnicodeStringValidateEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntstrsafe.h
req.include-header: Ntstrsafe.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RtlUnicodeStringValidateEx
req.alt-loc: Ntstrsafe.lib,Ntstrsafe.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
---

# RtlUnicodeStringValidateEx function



## -description
The <b>RtlUnicodeStringValidateEx</b> function validates the contents of a <a href="kernel.unicode_string">UNICODE_STRING</a> structure.


## -syntax

````
NTSTATUS RtlUnicodeStringValidateEx(
  _In_ PCUNICODE_STRING SourceString,
  _In_ DWORD            dwFlags
);
````


## -parameters

### -param SourceString [in]

Optional. A pointer to a <b>UNICODE_STRING</b> structure to be validated. This pointer can be <b>NULL</b>, but only if STRSAFE_IGNORE_NULLS is set in <i>dwFlags</i>.

### -param dwFlags [in]

The following flag is defined: 


### -param STRSAFE_IGNORE_NULLS 

If this flag is set, the source pointer can be <b>NULL</b>. <b>RtlUnicodeStringValidateEx</b> treats <b>NULL</b> source buffer pointers like empty strings (TEXT("")). 
</dd>
</dl>

## -returns
<b>RtlUnicodeStringValidateEx</b> returns one of the following NTSTATUS values. 
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>This <i>success</i> status means that the function completed successfully.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>This <i>error</i> status means that the function received an invalid input parameter. For more information, see the following list.

 

If STRSAFE_IGNORE_NULLS is not set in dwFlags, <b>RtlUnicodeStringValidateEx</b> returns the STATUS_INVALID_PARAMETER value when one of the following occurs:

For information about how to test NTSTATUS values, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565436">Using NTSTATUS Values</a>.

## -remarks
The <i>SourceString</i> pointer cannot be <b>NULL</b> unless the STRSAFE_IGNORE_NULLS flag is set.

For more information about the safe string functions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565508">Using Safe String Functions</a>. 

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows XP with Service Pack 1 (SP1) and later versions of Windows. 
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.h (include Ntstrsafe.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ntstrsafe.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.rtlunicodestringvalidate">RtlUnicodeStringValidate</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringValidateEx function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
