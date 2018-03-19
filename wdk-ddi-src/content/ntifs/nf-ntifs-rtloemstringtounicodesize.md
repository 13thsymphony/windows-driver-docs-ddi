---
UID: NF:ntifs.RtlOemStringToUnicodeSize
title: RtlOemStringToUnicodeSize macro
author: windows-driver-content
description: The RtlOemStringToUnicodeSize routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.
old-location: ifsk\rtloemstringtounicodesize.htm
old-project: ifsk
ms.assetid: e54d0e3f-4e46-43b5-8338-b6e2f2a14c56
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlOemStringToUnicodeSize, RtlOemStringToUnicodeSize routine [Installable File System Drivers], ifsk.rtloemstringtounicodesize, ntifs/RtlOemStringToUnicodeSize, rtlref_5f048569-d84e-43ee-8d51-1281f18c7ddf.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
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
-	RtlOemStringToUnicodeSize
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlOemStringToUnicodeSize function
The <b>RtlOemStringToUnicodeSize</b> routine determines the size, in bytes, that a given OEM string will be after it is translated into a null-terminated Unicode string.

## Syntax

````
ULONG RtlOemStringToUnicodeSize(
  _In_ POEM_STRING OemString
);
````

## Parameters

`STRING`

TBD


## Return Value

None

## Remarks

<b>RtlOemStringToUnicodeSize</b> can be called to determine how much memory to allocate when translating an OEM string to Unicode with <b>RtlOemStringToUnicodeString</b>. The returned value includes space for the NULL terminator. 

For information about other string-handling routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563884">Strings</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include FltKernel.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "< DISPATCH_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtloemstringtounicodestring.md">RtlOemStringToUnicodeString</a>



<a href="..\ntifs\nf-ntifs-rtloemstringtocountedunicodesize.md">RtlOemStringToCountedUnicodeSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558741">OEM_STRING</a>