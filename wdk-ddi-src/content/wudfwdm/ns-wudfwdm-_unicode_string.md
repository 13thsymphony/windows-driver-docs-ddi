---
UID: NS.WUDFWDM._UNICODE_STRING
title: _UNICODE_STRING
author: windows-driver-content
description: The UNICODE_STRING structure is used to define Unicode strings.
old-location: kernel\unicode_string.htm
old-project: kernel
ms.assetid: b02f29a9-1049-4e29-aac3-72bf0c70a21e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _UNICODE_STRING, UNICODE_STRING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wudfwdm.h
req.include-header: Wdm.h, Ntddk.h, Ntdef.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UNICODE_STRING
req.alt-loc: wudfwdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _UNICODE_STRING structure



## -description
The <b>UNICODE_STRING</b> structure is used to define Unicode strings.



## -syntax

````
typedef struct _UNICODE_STRING {
  USHORT Length;
  USHORT MaximumLength;
  PWSTR  Buffer;
} UNICODE_STRING, *PUNICODE_STRING;
````


## -struct-fields

### -field Length

The length, in bytes, of the string stored in <b>Buffer</b>.


### -field MaximumLength

The length, in bytes, of <b>Buffer</b>.


### -field Buffer

Pointer to a buffer used to contain a string of wide characters.


## -remarks
The <b>UNICODE_STRING</b> structure is used to pass Unicode strings. Use <a href="kernel.rtlunicodestringinit">RtlUnicodeStringInit</a> or   <a href="kernel.rtlunicodestringinitex">RtlUnicodeStringInitEx</a> to initialize a <b>UNICODE_STRING</b> structure.

If the string is null-terminated, <b>Length</b> does not include the trailing null character.

The <b>MaximumLength</b> is used to indicate the length of <b>Buffer</b> so that if the string is passed to a conversion routine such as <a href="kernel.rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a> the returned string does not exceed the buffer size.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfwdm.h (include Wdm.h, Ntddk.h, or Ntdef.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.oem_string">OEM_STRING</a>
</dt>
<dt>
<a href="kernel.ansi_string">ANSI_STRING</a>
</dt>
<dt>
<a href="kernel.rtlansistringtounicodesize">RtlAnsiStringToUnicodeSize</a>
</dt>
<dt>
<a href="kernel.rtlansistringtounicodestring">RtlAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="kernel.rtlfreeunicodestring">RtlFreeUnicodeString</a>
</dt>
<dt>
<a href="kernel.rtlinitunicodestring">RtlInitUnicodeString</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringtoansisize">RtlUnicodeStringToAnsiSize</a>
</dt>
<dt>
<a href="kernel.rtlunicodestringtoansistring">RtlUnicodeStringToAnsiString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20UNICODE_STRING structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

