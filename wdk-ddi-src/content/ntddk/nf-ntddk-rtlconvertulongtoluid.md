---
UID: NF:ntddk.RtlConvertUlongToLuid
title: RtlConvertUlongToLuid function
author: windows-driver-content
description: The RtlConvertUlongToLuid routine converts an unsigned long integer to a locally unique identifier (LUID), which is used by the system to represent a security privilege.
old-location: kernel\rtlconvertulongtoluid.htm
old-project: kernel
ms.assetid: f3c1e2d5-8bb8-486c-a78a-3ddde6ab64bd
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/RtlConvertUlongToLuid, RtlConvertUlongToLuid routine [Kernel-Mode Driver Architecture], RtlConvertUlongToLuid, k109_25b3458f-dc47-436f-af5b-7d6a9d8eeb2a.xml, kernel.rtlconvertulongtoluid
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	RtlConvertUlongToLuid
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# RtlConvertUlongToLuid function
The <b>RtlConvertUlongToLuid</b> routine converts an unsigned long integer to a locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>), which is used by the system to represent a security privilege.

## Syntax

````
LUID RtlConvertUlongToLuid(
  _In_ ULONG Ulong
);
````

## Parameters

`Ulong`

Specifies the unsigned long integer to convert.


## Return Value

<b>RtlConvertUlongToLuid</b> returns the converted <a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>.

## Remarks

<b>RtlConvertUlongToLuid</b> is used to convert a system-defined privilege value, passed as a ULONG, to a locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) used by the system to represent that privilege. Drivers typically pass a LUID to <b>SeSinglePrivilegeCheck</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | ntddk.h (include Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\ntddk\nf-ntddk-rtlconvertlongtoluid.md">RtlConvertLongToLuid</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff561842">RtlEqualLuid</a>

<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>

<a href="..\ntddk\nf-ntddk-sesingleprivilegecheck.md">SeSinglePrivilegeCheck</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlConvertUlongToLuid routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>