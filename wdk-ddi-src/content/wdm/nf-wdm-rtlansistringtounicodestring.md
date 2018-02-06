---
UID: NF:wdm.RtlAnsiStringToUnicodeString
title: RtlAnsiStringToUnicodeString function
author: windows-driver-content
description: RtlAnsiStringToUnicodeString converts the given ANSI source string into a Unicode string.
old-location: kernel\rtlansistringtounicodestring.htm
old-project: kernel
ms.assetid: 926d8919-42de-4e24-a223-ffbf412edf6d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlansistringtounicodestring, RtlAnsiStringToUnicodeString function [Kernel-Mode Driver Architecture], wdm/RtlAnsiStringToUnicodeString, k109_d27ee285-6d32-4ecb-994b-ba8a47f1e588.xml, RtlAnsiStringToUnicodeString
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlAnsiStringToUnicodeString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlAnsiStringToUnicodeString function
<b>RtlAnsiStringToUnicodeString</b> converts the given ANSI source string into a Unicode string.

## Syntax

````
NTSTATUS RtlAnsiStringToUnicodeString(
  _Inout_ PUNICODE_STRING DestinationString,
  _In_    PCANSI_STRING   SourceString,
  _In_    BOOLEAN         AllocateDestinationString
);
````

## Parameters

`DestinationString`

Pointer to a <a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a> structure to hold the converted Unicode string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently-specified buffer to hold the string.

`SourceString`

Pointer to the ANSI string to be converted to Unicode.

`AllocateDestinationString`

Specifies if this routine should allocate the buffer space for the destination string. If it does, the caller must deallocate the buffer by calling <a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>.


## Return Value

If the conversion succeeds, <b>RtlAnsiStringToUnicodeString</b> returns STATUS_SUCCESS. On failure, the routine does not allocate any memory.

## Remarks

The translation conforms to the current system locale information.

If caller sets <i>AllocateDestinationString</i> to <b>TRUE</b>, the routine replaces the <b>Buffer</b> member of <i>DestinationString</i> with a pointer to the buffer it allocates. The old value can be overwritten even when the routine returns an error status code.

This routine is not declared in a header file. However, you can copy the following declaration to your source code:
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSYSAPI
WCHAR
NTAPI
RtlAnsiCharToUnicodeChar(
    __inout PUCHAR *SourceCharacter
    );</pre>
</td>
</tr>
</table></span></div>You can use the following routines to convert single-byte and double-byte characters to Unicode characters:


<a href="..\wdm\nf-wdm-rtlansistringtounicodesize.md">RtlAnsiStringToUnicodeSize</a>


<b>RtlAnsiStringToUnicodeString</b>


<a href="..\ntifs\nf-ntifs-rtlmultibytetounicodesize.md">RtlMultiByteToUnicodeSize</a>



<a href="..\ntifs\nf-ntifs-rtlmultibytetounicoden.md">RtlMultiByteToUnicodeN</a>


For more information about these and other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

<b>RtlAnsiCharToUnicodeChar</b> has security deficiencies. Consider using the <b>RtlAnsiStringToUnicodeString</b> routine instead.

If, on entry, *<i>SourceCharacter</i> points to a one-byte buffer that contains the first byte of a two-byte character code, <b>RtlAnsiCharToUnicodeChar</b> overruns the buffer when it tries to read the second byte.

At system startup, the operating system determines the user language from the locale settings and installs the appropriate system ANSI code page. <b>RtlAnsiCharToUnicodeChar</b> uses this code page to convert a single-byte or double-byte character to the corresponding Unicode character.

If the system ANSI code page defines a single-byte character set (that is, the ANSI character set), <b>RtlAnsiCharToUnicodeChar</b> speeds up the conversion operation by simply <a href="https://msdn.microsoft.com/c8d392e7-90e1-4124-88d0-942b902a196a">zero-extending</a> an ANSI character in the range 0x00 to 0x7f to produce the corresponding Unicode character. The routine converts the ANSI value 0x5c to the backslash character ("\"), even if the single-byte code page defines this character as the yen sign.

If, on entry, *<i>SourceCharacter</i> points to an invalid character code, <b>RtlAnsiCharToUnicodeChar</b> returns the Unicode space character code, 0x0020. The following list shows examples of invalid character codes:
<ul>
<li>
The first byte of the character code is a value that is valid only as the second byte of a two-byte character code. 

</li>
<li>
The second byte of a two-byte character code is a value that is valid only as the first byte. 

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlansistringtounicodesize.md">RtlAnsiStringToUnicodeSize</a>

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\wdm\nf-wdm-rtlinitansistring.md">RtlInitAnsiString</a>

<a href="..\wdm\nf-wdm-rtlunicodestringtoansistring.md">RtlUnicodeStringToAnsiString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlAnsiStringToUnicodeString function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>