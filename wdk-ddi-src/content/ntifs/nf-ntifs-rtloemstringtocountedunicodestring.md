---
UID: NF:ntifs.RtlOemStringToCountedUnicodeString
title: RtlOemStringToCountedUnicodeString function
author: windows-driver-content
description: The RtlOemStringToCountedUnicodeString routine translates the specified source string into a Unicode string using the current system OEM code page.
old-location: ifsk\rtloemstringtocountedunicodestring.htm
old-project: ifsk
ms.assetid: bf36d51f-3e22-489b-a597-652f39242a30
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlOemStringToCountedUnicodeString, RtlOemStringToCountedUnicodeString routine [Installable File System Drivers], ifsk.rtloemstringtocountedunicodestring, ntifs/RtlOemStringToCountedUnicodeString, rtlref_f67c05d0-0a01-44a7-9718-b3f0ef83b8f0.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "< DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlOemStringToCountedUnicodeString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlOemStringToCountedUnicodeString function
The <b>RtlOemStringToCountedUnicodeString</b> routine translates the specified source string into a Unicode string using the current system OEM code page.

## Syntax

````
NTSTATUS RtlOemStringToCountedUnicodeString(
       PUNICODE_STRING DestinationString,
  _In_ PCOEM_STRING    SourceString,
  _In_ BOOLEAN         AllocateDestinationString
);
````

## Parameters

`DestinationString`

Pointer to a caller-allocated buffer to receive the translated Unicode string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the Unicode data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlOemStringToCountedUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly.

`SourceString`

Pointer to the OEM string to be translated into Unicode.

`AllocateDestinationString`

Set to <b>TRUE</b> if <b>RtlOemStringToCountedUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>.


## Return Value

If the operation succeeds, <b>RtlOemStringToCountedUnicodeString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated and no conversion was done.

## Remarks

<b>RtlOemStringToCountedUnicodeString</b> returns a translated string that does not include NULL terminator. It translates the given source string using the OEM code page that was installed as the current system code page at boot time. 

<b>RtlOemStringToCountedUnicodeString</b> does not modify the source string. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\ntifs\nf-ntifs-rtloemtounicoden.md">RtlOemToUnicodeN</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodesize.md">RtlOemStringToCountedUnicodeSize</a>



<a href="..\wudfwdm\nf-wudfwdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>