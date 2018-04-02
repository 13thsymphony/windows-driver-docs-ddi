---
UID: NF:wdm.RtlDowncaseUnicodeChar
title: RtlDowncaseUnicodeChar function
author: windows-driver-content
description: The RtlDowncaseUnicodeChar routine converts the specified Unicode character to lowercase.
old-location: kernel\rtldowncaseunicodechar.htm
old-project: kernel
ms.assetid: 1377a069-5065-4305-a48c-7a84f0071fc3
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlDowncaseUnicodeChar, RtlDowncaseUnicodeChar routine [Kernel-Mode Driver Architecture], k109_e9ba1cee-5de9-4f8f-b964-6668ddef36b7.xml, kernel.rtldowncaseunicodechar, wdm/RtlDowncaseUnicodeChar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.lib: Ntoskrnl.lib; Ntdll.lib
req.dll: Ntoskrnl.exe; Ntdll.dll
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Ntoskrnl.exe
-	Ntdll.dll
api_name:
-	RtlDowncaseUnicodeChar
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlDowncaseUnicodeChar function
The <b>RtlDowncaseUnicodeChar</b> routine converts the specified Unicode character to lowercase.

## Syntax

```
NTSYSAPI WCHAR RtlDowncaseUnicodeChar(
  WCHAR SourceCharacter
);
```

## Parameters

`SourceCharacter`

Specifies the character to convert.


## Return Value

<b>RtlDowncaseUnicodeChar</b> returns the lowercase value of the Unicode character.

## Remarks

Ntoskrnl.lib supports the <b>RtlDowncaseUnicodeChar</b> routine in the WDK for Windows 7 and later versions of Windows. Ntdll.dll exports the <b>RtlDowncaseUnicodeChar</b> entry point in Windows XP and later versions of Windows.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Ntoskrnl.lib; Ntdll.lib |
| **DLL** | Ntoskrnl.exe; Ntdll.dll |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff552237">RtlDowncaseUnicodeString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563003">RtlUpcaseUnicodeChar</a>