---
UID: NF:wdm.RtlUlongByteSwap
title: RtlUlongByteSwap macro
author: windows-driver-content
description: The RtlUlongByteSwap routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.
old-location: kernel\rtlulongbyteswap.htm
old-project: kernel
ms.assetid: 4c08a70e-5092-40fb-94fd-c3ef8a5537b5
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUlongByteSwap routine [Kernel-Mode Driver Architecture], wdm/RtlUlongByteSwap, k109_0d4753a3-859a-429f-bd07-66669f1b46e8.xml, kernel.rtlulongbyteswap, RtlUlongByteSwap
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUlongByteSwap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlUlongByteSwap function
The <b>RtlUlongByteSwap</b> routine reverses the ordering of the four bytes in a 32-bit unsigned integer value.

## Syntax

````
ULONG RtlUlongByteSwap(
  _In_ ULONG Source
);
````

## Parameters

`Source`




## Return Value

None

## Remarks

For example, if the <i>Source</i> parameter value is 0x12345678, the routine returns 0x78563412.

A typical use of this routine is to convert a ULONG value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohl</b> or <b>htonl</b>.

To reverse the ordering of bytes in a USHORT value, use the <a href="..\wdm\nf-wdm-rtlushortbyteswap.md">RtlUshortByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="..\wdm\nf-wdm-rtlulonglongbyteswap.md">RtlUlonglongByteSwap</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-rtlulonglongbyteswap.md">RtlUlonglongByteSwap</a>



<a href="..\wdm\nf-wdm-rtlushortbyteswap.md">RtlUshortByteSwap</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUlongByteSwap routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>