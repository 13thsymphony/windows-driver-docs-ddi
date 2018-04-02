---
UID: NF:wdm.RtlInitString
title: RtlInitString function
author: windows-driver-content
description: The RtlInitString routine initializes a counted string of 8-bit characters.
old-location: kernel\rtlinitstring.htm
old-project: kernel
ms.assetid: 954498b6-f611-4c88-99e1-a1812d512866
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlInitString, RtlInitString routine [Kernel-Mode Driver Architecture], k109_c0bd87a9-811c-4312-b2b4-e82bdbfa5b8c.xml, kernel.rtlinitstring, wdm/RtlInitString
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlInitString
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlInitString function
The <b>RtlInitString</b> routine initializes a counted string of 8-bit characters.

## Syntax

```
NTSYSAPI VOID RtlInitString(
  PSTRING               DestinationString,
  __drv_aliasesMem PCSZ SourceString
);
```

## Parameters

`DestinationString`

A pointer to the <b>STRING</b> structure to be initialized. The Ntdef.h header file defines this structure to be identical to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a> structure.

`SourceString`

A pointer to a null-terminated character string. This string is used to initialize the counted string pointed to by <i>DestinationString</i>.


## Return Value

None

## Remarks

This routine initializes a counted character string.

The routine copies the <i>SourceString</i> pointer value to the <b>Buffer</b> member of the <b>STRING</b> structure pointed to by <i>DestinationString</i>. The <b>Length</b> member of this structure is set to the length, in bytes, of the source string, excluding the terminating null. The <b>MaximumLength</b> member of the structure is set to the length, in bytes, of the source string, including the terminating null. If <i>SourceString</i> is <b>NULL</b>, <b>Length</b> and <b>MaximumLength</b> are both set to zero.

<b>RtlInitString</b> does not alter the source string pointed to by <i>SourceString</i>.

<div class="alert"><b>Note</b>  If the source string is longer than MAXUSHORT - 1 bytes, <b>RtlInitString</b> sets the <b>Length</b> member of the <b>STRING</b> structure pointed to by <i>DestinationString</i> to MAXUSHORT - 1, and sets the <b>MaximumLength</b> member of this structure to MAXUSHORT.  In this case, the <b>Length</b> and <b>MaximumLength</b> values misrepresent the length of the null-terminated source string, and relying on the accuracy of these values is potentially dangerous.</div>
<div> </div>
Callers of <b>RtlInitString</b> can be running at IRQL &lt;= DISPATCH_LEVEL if the <i>DestinationString</i> buffer is nonpageable. Usually, callers run at IRQL = PASSIVE_LEVEL because most other <b>Rtl<i>Xxx</i>String</b> routines cannot be called at IRQL &gt; PASSIVE_LEVEL.

The <b>RTL_CONSTANT_STRING</b> macro creates a string or Unicode string structure to hold a counted string.


<pre class="syntax">STRING RTL_CONSTANT_STRING(
  [in]  PCSZ SourceString
);

UNICODE_STRING RTL_CONSTANT_STRING(
  [in]  PCWSTR SourceString
);</pre>




<b>RTL_CONSTANT_STRING</b> returns either a string structure or Unicode string structure.

The <b>RTL_CONSTANT_STRING</b> macro replaces the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561918">RtlInitAnsiString</a>, <b>RtlInitString</b>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff561934">RtlInitUnicodeString</a> routines when passing a constant string.

You can use <b>RTL_CONSTANT_STRING</b> to initialize global variables.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | See Remarks section. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540605">ANSI_STRING</a>