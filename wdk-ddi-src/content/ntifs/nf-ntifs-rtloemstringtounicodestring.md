---
UID: NF:ntifs.RtlOemStringToUnicodeString
title: RtlOemStringToUnicodeString function
author: windows-driver-content
description: The RtlOemStringToUnicodeString routine translates a given source string into a null-terminated Unicode string using the current system OEM code page.
old-location: ifsk\rtloemstringtounicodestring.htm
old-project: ifsk
ms.assetid: 0420718f-3d0f-4f15-85ec-c2cdfa930023
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ntifs/RtlOemStringToUnicodeString, RtlOemStringToUnicodeString, ifsk.rtloemstringtounicodestring, RtlOemStringToUnicodeString routine [Installable File System Drivers], rtlref_6b1f3210-6b02-4f20-9887-b7efd0090b7f.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlOemStringToUnicodeString
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlOemStringToUnicodeString function
The <b>RtlOemStringToUnicodeString</b> routine translates a given source string into a null-terminated Unicode string using the current system OEM code page.

## Syntax

````
NTSTATUS RtlOemStringToUnicodeString(
       PUNICODE_STRING DestinationString,
  _In_ PCOEM_STRING    SourceString,
  _In_ BOOLEAN         AllocateDestinationString
);
````

## Parameters

`DestinationString`

Pointer to a caller-allocated buffer to receive the translated string. If <i>AllocateDestinationString</i> is <b>FALSE</b>, the caller must also allocate a buffer for the <b>Buffer</b> member of <i>DestinationString</i> to hold the null-terminated Unicode string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, <b>RtlOemStringToUnicodeString</b> allocates a buffer large enough to hold the string, passes a pointer to it in <b>Buffer</b>, and updates the length and maximum length members of <i>DestinationString</i> accordingly.

`SourceString`

Pointer to the OEM string to be translated to Unicode.

`AllocateDestinationString`

Set to <b>TRUE</b> if <b>RtlOemStringToUnicodeString</b> should allocate the buffer space for the <i>DestinationString</i>, <b>FALSE</b> otherwise. If this parameter is <b>TRUE</b>, the caller is responsible for freeing the buffer when it is no longer needed by calling <b>RtlFreeUnicodeString</b>.


## Return Value

<b>RtlOemStringToUnicodeString</b> returns STATUS_SUCCESS if it returns a translated string at <i>DestinationString</i>. Otherwise, no storage was allocated and no conversion was done.

## Remarks

<b>RtlOemStringToUnicodeString</b> translates the given source string using the OEM code page that was installed as the current system code page at system boot time. 

This routine does not modify the source string. It returns a NULL-terminated Unicode string. 

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

<a href="..\ntifs\nf-ntifs-rtlunicodestringtooemstring.md">RtlUnicodeStringToOemString</a>

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>

<a href="..\ntifs\nf-ntifs-rtloemtounicoden.md">RtlOemToUnicodeN</a>

<a href="..\ntifs\nf-ntifs-rtloemstringtounicodesize.md">RtlOemStringToUnicodeSize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlOemStringToUnicodeString routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>