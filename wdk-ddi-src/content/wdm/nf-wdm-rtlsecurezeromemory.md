---
UID: NF:wdm.RtlSecureZeroMemory
title: RtlSecureZeroMemory function
author: windows-driver-content
description: The RtlSecureZeroMemory routine fills a block of memory with zeros in a way that is guaranteed to be secure.
old-location: kernel\rtlsecurezeromemory.htm
old-project: kernel
ms.assetid: b7a9beaf-5eca-4fb0-af63-06c002297085
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlSecureZeroMemory, RtlSecureZeroMemory routine [Kernel-Mode Driver Architecture], k109_8bcffbc1-2930-416b-a192-b70c477d1910.xml, kernel.rtlsecurezeromemory, wdm/RtlSecureZeroMemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows. (Because the routine is declared inline, the body of the routine can be included in earlier versions of the operating system.)
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
req.lib: 
req.dll: 
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RtlSecureZeroMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlSecureZeroMemory function
The <b>RtlSecureZeroMemory</b> routine fills a block of memory with zeros in a way that is guaranteed to be secure.

## Syntax

```
PVOID RtlSecureZeroMemory(
  PVOID  ptr,
  SIZE_T cnt
);
```

## Parameters

`ptr`

Pointer to the memory buffer to be filled with zeros.

`cnt`

Specifies the number of bytes to be filled with zeros.


## Return Value

None

## Remarks

The effect of <b>RtlSecureZeroMemory</b> is identical to that of <a href="https://msdn.microsoft.com/library/windows/hardware/ff563610">RtlZeroMemory</a>, except that it is guaranteed to zero the memory location, even if it is not subsequently written to. (The compiler can optimize away a call to <b>RtlZeroMemory</b>, if it determines that the caller does not access that memory range again.)

Use <b>RtlSecureZeroMemory</b> to guarantee that sensitive information has been zeroed out. For example, suppose that a function uses a local array variable to store password information. Once the function exits, the password information can remain in the same memory location unless zeroed out by <b>RtlSecureZeroMemory</b>.

<b>RtlSecureZeroMemory</b> is slower than <b>RtlZeroMemory</b>; therefore, if security is not an issue, use <b>RtlZeroMemory</b> instead.

Callers of <b>RtlSecureZeroMemory</b> can be running at any IRQL if the <i>ptr</i> block is in nonpaged pool. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Server 2003 and later versions of Windows. (Because the routine is declared inline, the body of the routine can be included in earlier versions of the operating system.)  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561870">RtlFillMemory</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563610">RtlZeroMemory</a>