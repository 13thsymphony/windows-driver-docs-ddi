---
UID: NF:ntifs.RtlLengthSid
title: RtlLengthSid function
author: windows-driver-content
description: The RtlLengthSid routine returns the length, in bytes, of a valid security identifier (SID).
old-location: ifsk\rtllengthsid.htm
old-project: ifsk
ms.assetid: 5d96061d-f1a2-4e45-b76e-5ada61d8accd
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlLengthSid, RtlLengthSid routine [Installable File System Drivers], ifsk.rtllengthsid, ntifs/RtlLengthSid, rtlref_8bbf6a04-413c-4f50-9f51-1ddd8bce58ff.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	ntdll.dll
api_name:
-	RtlLengthSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlLengthSid function
The <b>RtlLengthSid</b> routine returns the length, in bytes, of a valid security identifier (SID).

## Syntax

````
ULONG RtlLengthSid(
  _In_ PSID Sid
);
````

## Parameters

`Sid`

Pointer to the SID structure. Must point to a valid SID.


## Return Value

If the SID structure is valid, <b>RtlLengthSid</b> returns the length, in bytes, of the SID structure.

If the SID structure is not valid, the return value is undefined. Before calling <b>RtlLengthSid</b>, pass the SID to <a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a> to verify that it is valid.

## Remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\nf-ntifs-rtlequalsid.md">RtlEqualSid</a>



<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>



<a href="..\ntifs\nf-ntifs-rtlinitializesid.md">RtlInitializeSid</a>



<a href="..\ntifs\nf-ntifs-rtllengthrequiredsid.md">RtlLengthRequiredSid</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>