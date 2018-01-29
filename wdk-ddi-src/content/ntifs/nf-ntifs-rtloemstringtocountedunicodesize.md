---
UID : NF:ntifs.RtlOemStringToCountedUnicodeSize
title : RtlOemStringToCountedUnicodeSize macro
author : windows-driver-content
description : The RtlOemStringToCountedUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a counted Unicode string.
old-location : ifsk\rtloemstringtocountedunicodesize.htm
old-project : ifsk
ms.assetid : a618420f-ea69-471d-82a0-1e86f85e270b
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ifsk.rtloemstringtocountedunicodesize, RtlOemStringToCountedUnicodeSize routine [Installable File System Drivers], RtlOemStringToCountedUnicodeSize, ntifs/RtlOemStringToCountedUnicodeSize, rtlref_dc10fcb6-356a-4c09-aea6-c386030039f0.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : ntifs.h
req.dll : 
req.irql : < DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# RtlOemStringToCountedUnicodeSize function
The <b>RtlOemStringToCountedUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a counted Unicode string.

## Syntax

````
ULONG RtlOemStringToCountedUnicodeSize(
  _In_ POEM_STRING OemString
);
````

## Parameters

`STRING`

TBD


## Return Value

None

## Remarks

<b>RtlOemStringToCountedUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToCountedUnicodeString</b>. The returned value does not include space for a NULL terminator for the Unicode string.

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodestring.md">RtlOemStringToCountedUnicodeString</a>

<a href="..\ntifs\nf-ntifs-rtloemstringtounicodesize.md">RtlOemStringToUnicodeSize</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlOemStringToCountedUnicodeSize routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>