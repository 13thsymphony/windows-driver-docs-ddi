---
UID: NF:ntifs.RtlUnicodeStringToCountedOemString
title: RtlUnicodeStringToCountedOemString function
author: windows-driver-content
description: The RtlUnicodeStringToCountedOemString routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page.
old-location: ifsk\rtlunicodestringtocountedoemstring.htm
old-project: ifsk
ms.assetid: 7479d5d0-69d0-42b8-9aa1-5eab8b71b118
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlUnicodeStringToCountedOemString, RtlUnicodeStringToCountedOemString routine [Installable File System Drivers], ifsk.rtlunicodestringtocountedoemstring, ntifs/RtlUnicodeStringToCountedOemString, rtlref_dbc62228-043f-43f1-bd19-464adf37b693.xml
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
-	RtlUnicodeStringToCountedOemString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlUnicodeStringToCountedOemString function
The <b>RtlUnicodeStringToCountedOemString</b> routine translates the specified Unicode source string into a counted OEM string using the current system OEM code page.

## Syntax

````
NTSTATUS RtlUnicodeStringToCountedOemString(
       POEM_STRING      DestinationString,
  _In_ PCUNICODE_STRING SourceString,
  _In_ BOOLEAN          AllocateDestinationString
);
````

## Parameters

`DestinationString`

Pointer to a caller-allocated buffer to receive the counted OEM string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the OEM data. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlUnicodeStringToCountedOemString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly.

`SourceString`

Pointer to the source Unicode string to be translated.

`AllocateDestinationString`

Set to <b>TRUE</b> if <b>RtlUnicodeStringToCountedOemString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeOemString</b>.


## Return Value

<b>RtlUnicodeStringToCountedOemString</b> returns STATUS_SUCCESS if the string at <i>DestinationString</i> is translated. Otherwise, no storage was allocated, and no conversion was performed. This routine returns STATUS_UNMAPPABLE_CHARACTER if it cannot translate a character in the given <i>SourceString</i>.

## Remarks

<b>RtlUnicodeStringToCountedOemString</b> returns a translated string that does not include a NULL terminator. It translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

<b>RtlUnicodeStringToCountedOemString</b> does not modify the source string.

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

<a href="..\ntifs\nf-ntifs-rtlfreeoemstring.md">RtlFreeOemString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>



<a href="..\ntifs\nf-ntifs-rtlunicodetooemn.md">RtlUnicodeToOemN</a>



<a href="..\ntifs\nf-ntifs-rtlupcaseunicodestringtocountedoemstring.md">RtlUpcaseUnicodeStringToCountedOemString</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>



<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>



<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>