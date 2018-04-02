---
UID: NS:wudfwdm._UNICODE_STRING
title: "_UNICODE_STRING"
author: windows-driver-content
description: The UNICODE_STRING structure is used to define Unicode strings.
old-location: kernel\unicode_string.htm
old-project: kernel
ms.assetid: b02f29a9-1049-4e29-aac3-72bf0c70a21e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUNICODE_STRING, PUNICODE_STRING, PUNICODE_STRING structure pointer [Kernel-Mode Driver Architecture], UNICODE_STRING, UNICODE_STRING structure [Kernel-Mode Driver Architecture], _UNICODE_STRING, kernel.unicode_string, kstruct_d_9f862aaa-4cd6-4420-8255-ad577d8a8c59.xml, wudfwdm/PUNICODE_STRING, wudfwdm/UNICODE_STRING"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wudfwdm.h
api_name:
-	UNICODE_STRING
product:
- Windows
targetos: Windows
req.typenames: UNICODE_STRING
req.product: Windows 10 or later.
---

# _UNICODE_STRING structure
The <b>UNICODE_STRING</b> structure is used to define Unicode strings.

## Syntax
````
typedef struct _UNICODE_STRING {
  USHORT Length;
  USHORT MaximumLength;
  PWSTR  Buffer;
} UNICODE_STRING, *PUNICODE_STRING;
````

## Members


`Length`

The length, in bytes, of the string stored in <b>Buffer</b>.

`MaximumLength`

The length, in bytes, of <b>Buffer</b>.

## Remarks
The <b>UNICODE_STRING</b> structure is used to pass Unicode strings. Use <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinit.md">RtlUnicodeStringInit</a> or   <a href="..\ntstrsafe\nf-ntstrsafe-rtlunicodestringinitex.md">RtlUnicodeStringInitEx</a> to initialize a <b>UNICODE_STRING</b> structure.

If the string is null-terminated, <b>Length</b> does not include the trailing null character.

The <b>MaximumLength</b> is used to indicate the length of <b>Buffer</b> so that if the string is passed to a conversion routine such as <a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a> the returned string does not exceed the buffer size.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfwdm.h (include Wdm.h, Ntddk.h, Ntdef.h) |

## See Also

<a href="..\wudfwdm\nf-wudfwdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>



<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlinitunicodestring.md">RtlInitUnicodeString</a>



<a href="..\wdm\nf-wdm-rtlansistringtounicodesize.md">RtlAnsiStringToUnicodeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>



<a href="..\wdm\nf-wdm-rtlunicodestringtoansisize.md">RtlUnicodeStringToAnsiSize</a>