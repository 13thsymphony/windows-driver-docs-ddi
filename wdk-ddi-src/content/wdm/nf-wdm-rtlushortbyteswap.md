---
UID: NF:wdm.RtlUshortByteSwap
title: RtlUshortByteSwap function
author: windows-driver-content
description: The RtlUshortByteSwap routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.
old-location: kernel\rtlushortbyteswap.htm
old-project: kernel
ms.assetid: 83f6a599-0b35-4a02-b20f-80abcc6eae4f
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlUshortByteSwap routine [Kernel-Mode Driver Architecture], RtlUshortByteSwap, wdm/RtlUshortByteSwap, kernel.rtlushortbyteswap, k109_36a00506-f4e3-467b-9494-c13b2ea70a1f.xml
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
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlUshortByteSwap
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlUshortByteSwap function
The <b>RtlUshortByteSwap</b> routine reverses the ordering of the two bytes in a 16-bit unsigned integer value.

## Syntax

````
USHORT RtlUshortByteSwap(
  _In_ USHORT Source
);
````

## Parameters

`Source`

A USHORT value to convert to a byte-swapped version.


## Return Value

The byte-swapped version of the <i>Source</i> input parameter value.

## Remarks

For example, if the <i>Source</i> parameter value is 0x1234, the routine returns 0x3412.

A typical use of this routine is to convert a USHORT value from little-endian byte format to big-endian byte format, and vice versa.

Use this routine instead of <b>ntohs</b> or <b>htons</b>.

To reverse the ordering of bytes in a ULONG value, use the <a href="..\wdm\nf-wdm-rtlulongbyteswap.md">RtlUlongByteSwap</a> routine. To reverse ordering of bytes in a ULONGLONG value, use the <a href="..\wdm\nf-wdm-rtlulonglongbyteswap.md">RtlUlonglongByteSwap</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-rtlulonglongbyteswap.md">RtlUlonglongByteSwap</a>

<a href="..\wdm\nf-wdm-rtlulongbyteswap.md">RtlUlongByteSwap</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlUshortByteSwap routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>