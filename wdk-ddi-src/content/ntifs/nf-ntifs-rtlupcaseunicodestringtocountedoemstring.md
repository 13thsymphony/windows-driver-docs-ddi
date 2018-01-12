---
UID: NF:ntifs.RtlUpcaseUnicodeStringToCountedOemString
title: RtlUpcaseUnicodeStringToCountedOemString function
author: windows-driver-content
description: The RtlUpcaseUnicodeStringToCountedOemString routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page.
old-location: ifsk\rtlupcaseunicodestringtocountedoemstring.htm
old-project: ifsk
ms.assetid: c1e466d7-892f-4049-a6c2-60ab8f960acb
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RtlUpcaseUnicodeStringToCountedOemString
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
req.alt-api: RtlUpcaseUnicodeStringToCountedOemString
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
req.typenames: TOKEN_TYPE
---

# RtlUpcaseUnicodeStringToCountedOemString function



## -description
The <b>RtlUpcaseUnicodeStringToCountedOemString</b> routine translates a given Unicode source string into an uppercase counted OEM string using the current system OEM code page. 



## -syntax

````
NTSTATUS RtlUpcaseUnicodeStringToCountedOemString(
       POEM_STRING      DestinationString,
  _In_ PCUNICODE_STRING SourceString,
  _In_ BOOLEAN          AllocateDestinationString
);
````


## -parameters

### -param DestinationString 

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUpcaseUnicodeStringToCountedOemString </b>allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly. 


### -param SourceString [in]

Pointer to the Unicode string to be translated. 


### -param AllocateDestinationString [in]

Set to <b>TRUE</b> if <b>RtlUpcaseUnicodeStringToCountedOemString </b>should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>. 


## -returns
<b>RtlUpcaseUnicodeStringToCountedOemString</b> returns STATUS_SUCCESS if it returns a translated string at <i>DestinationString</i>. Otherwise, no storage was allocated, nor was any conversion performed. It returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given <i>SourceString</i>. 


## -remarks
<b>RtlUpcaseUnicodeStringToCountedOemString</b> returns a string that is not null-terminated. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time, and converts the translated string to uppercase. 

To find a best-match mapping for any special characters, such as a copyright character, in the given source string, <b>RtlUpcaseUnicodeStringToCountedOemString</b> performs the following operations: 

Translates a copy of the Unicode string at <i>SourceString</i> into an OEM string

Translates the OEM string back into Unicode

Converts this new Unicode string to uppercase

Translates the uppercase Unicode string into a counted OEM string and returns it at <i>DestinationString</i>

This routine does not modify the source string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>. 


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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlfreeoemstring.md">RtlFreeOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodestringtocountedoemstring.md">RtlUnicodeStringToCountedOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemsize.md">RtlUnicodeStringToOemSize</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtooemstring.md">RtlUpcaseUnicodeStringToOemString</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-rtlupcaseunicodetooemn.md">RtlUpcaseUnicodeToOemN</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlUpcaseUnicodeStringToCountedOemString routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

