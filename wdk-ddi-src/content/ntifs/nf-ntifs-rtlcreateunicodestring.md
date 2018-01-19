---
UID : NF:ntifs.RtlCreateUnicodeString
title : RtlCreateUnicodeString function
author : windows-driver-content
description : The RtlCreateUnicodeString routine creates a new counted Unicode string.
old-location : ifsk\rtlcreateunicodestring.htm
old-project : ifsk
ms.assetid : f101fc66-40a9-4077-b651-cef0a0e247d4
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlCreateUnicodeString
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : This routine is available on Microsoft Windows 2000 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlCreateUnicodeString
req.alt-loc : NtosKrnl.exe,Ntdll.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql : PASSIVE_LEVEL
req.typenames : TOKEN_TYPE
---


# RtlCreateUnicodeString function
The <b>RtlCreateUnicodeString</b> routine creates a new counted Unicode string.

## Syntax

````
BOOLEAN RtlCreateUnicodeString(
  _Out_ PUNICODE_STRING DestinationString,
  _In_  PCWSTR          SourceString
);
````

## Parameters

`DestinationString`

Pointer to the newly allocated and initialized Unicode string.

`SourceString`

Pointer to a null-terminated Unicode string with which to initialize the new string.


## Return Value

<b>RtlCreateUnicodeString</b> returns <b>TRUE</b> if the Unicode string was successfully created, <b>FALSE</b> otherwise.

## Remarks

The <i>DestinationString</i> is allocated from paged pool. The caller is responsible for freeing the <i>DestinationString</i> by calling <b>RtlFreeUnicodeString</b>.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-rtlfreeunicodestring.md">RtlFreeUnicodeString</a>
</dt>
<dt>
<a href="..\wudfwdm\ns-wudfwdm-_unicode_string.md">UNICODE_STRING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlCreateUnicodeString routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>