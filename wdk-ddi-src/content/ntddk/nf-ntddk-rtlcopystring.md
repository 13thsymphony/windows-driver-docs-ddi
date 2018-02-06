---
UID: NF:ntddk.RtlCopyString
title: RtlCopyString function
author: windows-driver-content
description: The RtlCopyString routine copies a source string to a destination string.
old-location: kernel\rtlcopystring.htm
old-project: kernel
ms.assetid: 5295be15-b42e-4e5b-8257-434fb9ed6c83
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlCopyString, RtlCopyString routine [Kernel-Mode Driver Architecture], kernel.rtlcopystring, k109_c68983f1-ec02-405f-a3a6-d1f3884fe303.xml, ntddk/RtlCopyString
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
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
req.irql: Any level (See Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlCopyString
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlCopyString function
The <b>RtlCopyString</b> routine copies a source string to a destination string.

## Syntax

````
VOID RtlCopyString(
  _Out_          PSTRING DestinationString,
  _In_opt_ const STRING  *SourceString
);
````

## Parameters

`DestinationString`

A pointer to the destination string buffer.

`SourceString`

A pointer to the source string buffer.


## Return Value

None

## Remarks

The<i> DestinationString </i><b>Length</b> is set to zero if no source string is supplied. The <b>MaximumLength</b> and <b>Buffer</b> members of the <i>DestinationString</i> are not modified by this routine.

The number of bytes copied from the <i>SourceString</i> is either the length of <i>SourceString</i> or the maximum length of <i>DestinationString</i>, whichever is smaller. 

The <i>DestinationString</i> and <i>SourceString</i> buffers must be resident if the caller is running at IRQL &gt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Universal |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="..\wdm\nf-wdm-rtlcopyunicodestring.md">RtlCopyUnicodeString</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCopyString routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>