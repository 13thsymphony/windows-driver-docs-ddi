---
UID: NF:wdm.RtlEqualUnicodeString
title: RtlEqualUnicodeString function
author: windows-driver-content
description: The RtlEqualUnicodeString routine compares two Unicode strings to determine whether they are equal.
old-location: kernel\rtlequalunicodestring.htm
old-project: kernel
ms.assetid: ba50fcac-acb1-43de-aacc-b47845f19f44
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlEqualUnicodeString routine [Kernel-Mode Driver Architecture], k109_59d7c507-968a-4cf5-b1f0-91c8cd7ccb64.xml, wdm/RtlEqualUnicodeString, RtlEqualUnicodeString, kernel.rtlequalunicodestring
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
-	Ntdll.dll
apiname:
-	RtlEqualUnicodeString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlEqualUnicodeString function
The <b>RtlEqualUnicodeString</b> routine compares two Unicode strings to determine whether they are equal.

## Syntax

````
BOOLEAN RtlEqualUnicodeString(
  _In_ PCUNICODE_STRING String1,
  _In_ PCUNICODE_STRING String2,
  _In_ BOOLEAN          CaseInSensitive
);
````

## Parameters

`String1`

Pointer to the first Unicode string.

`String2`

Pointer to the second Unicode string.

`CaseInSensitive`

If <b>TRUE</b>, case should be ignored when doing the comparison.


## Return Value

<b>RtlEqualUnicodeString</b> returns <b>TRUE</b> if the two Unicode strings are equal; otherwise, it returns <b>FALSE</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\ntddk\nf-ntddk-rtlequalstring.md">RtlEqualString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlEqualUnicodeString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>