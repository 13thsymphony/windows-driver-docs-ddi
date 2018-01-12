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
ms.keywords: RtlUnicodeStringToAnsiString
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
req.alt-api: RtlUnicodeStringToAnsiString
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
req.irql: PASSIVE_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# RtlUnicodeStringToAnsiString function



## -description
The <b>RtlUnicodeStringToAnsiString</b> routine converts a given Unicode string into an ANSI string.



## -syntax

````
NTSTATUS RtlUnicodeStringToAnsiString(
  _Inout_ PANSI_STRING     DestinationString,
  _In_    PCUNICODE_STRING SourceString,
  _In_    BOOLEAN          AllocateDestinationString
);
````


## -parameters

### -param DestinationString [in, out]

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure to hold the converted ANSI string. If <i>AllocateDestinationString</i> is <b>TRUE</b>, the routine allocates a new buffer to hold the string data, and updates the <b>Buffer</b> member of <i>DestinationString</i> to point to the new buffer. Otherwise, the routine uses the currently specified buffer to hold the string. 


### -param SourceString [in]

Pointer to the Unicode source string to be converted to ANSI.


### -param AllocateDestinationString [in]

<b>TRUE</b> if this routine is to allocate the buffer space for the <i>DestinationString</i>. If it does, the buffer must be deallocated by calling <a href="..\wdm\nf-wdm-rtlfreeansistring.md">RtlFreeAnsiString</a>.


## -returns
If the conversion succeeds, <b>RtlUnicodeStringToAnsiString</b> returns STATUS_SUCCESS. Otherwise, no storage was allocated, and no conversion was done.


## -remarks
The translation is done in accord with the current system-locale information.


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
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlansistringtounicodestring.md">RtlAnsiStringToUnicodeString</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-rtlfreeansistring.md">RtlFreeAnsiString</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUnicodeStringToAnsiString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

