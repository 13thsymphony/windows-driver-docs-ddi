---
UID : NF:ntifs.RtlRandomEx
title : RtlRandomEx function
author : windows-driver-content
description : The RtlRandomEx routine returns a random number that was generated from a given seed value.
old-location : ifsk\rtlrandomex.htm
old-project : ifsk
ms.assetid : 2a5c70da-69dc-431c-9ce9-908633045372
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlRandomEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h, Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RtlRandomEx
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : < DISPATCH_LEVEL
req.typenames : TOKEN_TYPE
---


# RtlRandomEx function
The <b>RtlRandomEx</b> routine returns a random number that was generated from a given seed value.

## Syntax

````
ULONG RtlRandomEx(
  _Inout_ PULONG Seed
);
````

## Parameters

`Seed`

Unsigned long value from which to generate a random number.


## Return Value

<b>RtlRandomEx</b> returns a random number in the range [0..MAXLONG-1].

## Remarks

<b>RtlRandomEx</b> returns values that are uniformly distributed over the range from zero to the maximum possible LONG value less 1 if it is called repeatedly with the same <i>Seed</i>.

The <b>RtlRandomEx</b> function is an improved version of the <b>RtlRandom</b> function. Compared with the <b>RtlRandom</b> function, <b>RtlRandomEx</b> is twice as fast and produces better random numbers since the period of the random numbers generated is comparatively higher.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h, Fltkernel.h) |
| **Library** |  |
| **IRQL** | < DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-rtlrandom.md">RtlRandom</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlRandomEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>