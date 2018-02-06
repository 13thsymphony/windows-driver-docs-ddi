---
UID: NF:wdm.RtlUnicodeStringToAnsiString
title: RtlUnicodeStringToAnsiString function
author: windows-driver-content
description: The RtlUnicodeStringToAnsiString routine converts a given Unicode string into an ANSI string.
old-location: kernel\rtlunicodestringtoansistring.htm
old-project: kernel
ms.assetid: d05b366c-0b09-4a82-8727-e5c39b82bf7f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.rtlunicodestringtoansistring, k109_50e549a0-61fa-4a0f-b43f-de2f4c6dba31.xml, RtlUnicodeStringToAnsiString, wdm/RtlUnicodeStringToAnsiString, RtlUnicodeStringToAnsiString routine [Kernel-Mode Driver Architecture]
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
-	RtlUnicodeStringToAnsiString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlUnicodeStringToAnsiString function
The <b>RtlUnicodeStringToAnsiString</b> routine converts a given Unicode string into an ANSI string.

## Syntax

````
NTSTATUS RtlUnicodeStringToAnsiString(
  _Inout_ PANSI_STRING     DestinationString,
  _In_    PCUNICODE_STRING SourceString,
  _In_    BOOLEAN          AllocateDestinationString
);
````

## Parameters

`DestinationString`

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure to hold the converted ANSI string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string.

`SourceString`

Pointer to the Unicode source string to be converted to ANSI.

`AllocateDestinationString`

<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="..\wdm\nf-wdm-rtlfreeansistring.md">RtlFreeAnsiString</a>.


## Return Value

If the conversion succeeds, <b>RtlUnicodeStringToAnsiString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.

## Remarks

The translation is done in accord with the current system-locale information.

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

<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>

<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>

<a href="..\wdm\nf-wdm-rtlfreeansistring.md">RtlFreeAnsiString</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringToAnsiString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>