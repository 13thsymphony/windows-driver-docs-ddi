---
UID: NF:ntifs.RtlEqualSid
title: RtlEqualSid function
author: windows-driver-content
description: The RtlEqualSid routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.
old-location: ifsk\rtlequalsid.htm
old-project: ifsk
ms.assetid: 4976fc27-c28a-46ec-ac07-19505cda8f14
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlEqualSid, RtlEqualSid routine [Installable File System Drivers], ifsk.rtlequalsid, ntifs/RtlEqualSid, rtlref_bc81c0ad-e0e6-4133-a423-4f6c4c264286.xml
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
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: Any
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlEqualSid
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlEqualSid function
The <b>RtlEqualSid</b> routine determines whether two security identifier (SID) values are equal. Two SIDs must match exactly to be considered equal.

## Syntax

````
BOOLEAN RtlEqualSid(
  _In_ PSID Sid1,
  _In_ PSID Sid2
);
````

## Parameters

`Sid1`

Pointer to the first SID structure to compare. Must point to a valid SID.

`Sid2`

Pointer to the second SID structure to compare. Must point to a valid SID.


## Return Value

<b>RtlEqualSid</b> returns <b>TRUE</b> if the SID structures are equal, <b>FALSE</b> otherwise. If either SID structure is invalid, the return value is undefined.

## Remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | Any |

## See Also

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlvalidsid.md">RtlValidSid</a>



<a href="..\ntifs\nf-ntifs-rtlcopysid.md">RtlCopySid</a>



<a href="..\ntifs\nf-ntifs-rtlequalprefixsid.md">RtlEqualPrefixSid</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlEqualSid routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>