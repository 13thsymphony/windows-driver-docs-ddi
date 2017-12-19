---
UID: NF.ntifs.RtlGenerate8dot3Name
title: RtlGenerate8dot3Name function
author: windows-driver-content
description: The RtlGenerate8dot3Name routine generates a short (8.3) name for the specified long file name.
old-location: ifsk\rtlgenerate8dot3name.htm
old-project: ifsk
ms.assetid: 7e8f84c4-c251-4f80-a8fc-465e44c14405
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RtlGenerate8dot3Name
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
req.alt-api: RtlGenerate8dot3Name
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

# RtlGenerate8dot3Name function



## -description
The <b>RtlGenerate8dot3Name</b> routine generates a short (8.3) name for the specified long file name. 



## -syntax

````
NTSTATUS RtlGenerate8dot3Name(
  _In_    PCUNICODE_STRING       Name,
  _In_    BOOLEAN                AllowExtendedCharacters,
  _Inout_ PGENERATE_NAME_CONTEXT Context,
  _Inout_ PUNICODE_STRING        Name8dot3
);
````


## -parameters

### -param Name [in]

Pointer to a Unicode string containing the long name for the file. Any leading periods in this file name are skipped during generation of a corresponding short name. 


### -param AllowExtendedCharacters [in]

Set to <b>TRUE</b> if the generated short file name can contain extended characters. Set to <b>FALSE</b> if the generated short file name must contain only characters within the current code page's ANSI or OEM range from 0x20 (space) through 0x7f (DEL). 


### -param Context [in, out]

Pointer to a caller-allocated buffer for use by <b>RtlGenerate8dot3Name</b>. Before calling <b>RtlGenerate8dot3Name</b> for the first time to translate the given long file name, the caller is responsible for filling the buffer with zeros.


### -param Name8dot3 [in, out]

Pointer to a caller-allocated buffer to receive the generated short file name. The size of this buffer must be at least 24 bytes (12 Unicode characters). 


## -returns
None


## -remarks
<b>RtlGenerate8dot3Name</b> returns a generated short name with at most eight characters, followed immediately by a period and up to three more characters. 

<b>RtlGenerate8dot3Name</b> can be called repeatedly. For example, if the initially generated short name is a duplicate of an existing file name, the caller can pass the same parameters to <b>RtlGenerate8dot3Name</b> again. In this case, the buffer at <i>Context</i> should not be reinitialized with zeros. This buffer should be zeroed only for the initial call to translate a given long name. On repeated calls for the same long name, <b>RtlGenerate8dot3Name</b> stores private context information in this buffer to prevent name collisions. 

Two calls to <b>RtlGenerate8dot3Name</b> with the same <i>Name</i> and <i>Context</i> are not guaranteed to return the same result. Callers should assume that the mapping of long name to short name is nondeterministic. 

<b>RtlGenerate8dot3Name</b> translates the given long name using the current system code page, discarding any invalid or superfluous characters in the input long name. When <i>AllowExtendedCharacters</i> is set to <b>TRUE</b>, ANSI or double-byte character set (DBCS) characters that map to uppercase OEM characters can become part of a returned short name. 

<b>RtlGenerate8dot3Name</b> returns a short file name with uppercase alphabetic characters. It returns underscores in the generated short name for any of the following characters that it encounters in the given long name:

Colons and semicolons 

Commas 

Plus and equal signs 

Square brackets 

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
<a href="ifsk.rtlisnamelegaldos8dot3">RtlIsNameLegalDOS8Dot3</a>
</dt>
<dt>
<a href="ifsk.rtlisvalidoemcharacter">RtlIsValidOemCharacter</a>
</dt>
<dt>
<a href="kernel.unicode_string">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlGenerate8dot3Name routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

