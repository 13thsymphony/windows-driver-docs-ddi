---
UID: NF:ntifs.RtlInitializeSidEx
title: RtlInitializeSidEx function
author: windows-driver-content
description: The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure.
old-location: ifsk\rtlinitializesidex.htm
old-project: ifsk
ms.assetid: 367D8BC1-07F4-474E-913A-5F825320A70C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RtlInitializeSidEx, RtlInitializeSidEx routine [Installable File System Drivers], ifsk.rtlinitializesidex, ntifs/RtlInitializeSidEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Windows 10 and later.
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
api_name:
-	RtlInitializeSidEx
product: Windows
targetos: Windows
req.typenames: TOKEN_TYPE
---


# RtlInitializeSidEx function
The <b>RtlInitializeSidEx</b> routine initializes a pre-allocated security identifier (SID) structure.

## Syntax

````
NTSTATUS RtlInitializeSidEx(
  _Out_ PSID                      Sid,
  _In_  PSID_IDENTIFIER_AUTHORITY IdentifierAuthority,
  _In_  UCHAR                     SubAuthorityCount,
                                  ...
);
````

## Parameters

`Sid`

Pointer to a caller-allocated SID structure to be initialized.

`IdentifierAuthority`

Pointer to an <a href="..\ntifs\ns-ntifs-_sid_identifier_authority.md">SID_IDENTIFIER_AUTHORITY</a> structure to set in the SID structure.

`SubAuthorityCount`

Number of sub-authorities to set in the SID.

`Arg1`




## Return Value

<b>RtlInitializeSid</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The SID was successfully initialized.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified <i>SubAuthorityCount</i> value is invalid.

</td>
</tr>
</table>

## Remarks

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This routine is available on Windows 10 and later.  |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\ns-ntifs-_sid_identifier_authority.md">SID_IDENTIFIER_AUTHORITY</a>



<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>



<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>