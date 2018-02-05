---
UID : NF:ntifs.RtlInitializeSidEx
title : RtlInitializeSidEx function
author : windows-driver-content
description : The RtlInitializeSidEx routine initializes a pre-allocated security identifier (SID) structure.
old-location : ifsk\rtlinitializesidex.htm
old-project : ifsk
ms.assetid : 367D8BC1-07F4-474E-913A-5F825320A70C
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RtlInitializeSidEx routine [Installable File System Drivers], ntifs/RtlInitializeSidEx, ifsk.rtlinitializesidex, RtlInitializeSidEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : This routine is available on Windows 10 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : "<= APC_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
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
| **Windows version** | This routine is available on Windows 10 and later. This routine is available on Windows 10 and later. |
| **Target Platform** | Universal |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL" |

## See Also

<a href="..\ntifs\ns-ntifs-_sid_identifier_authority.md">SID_IDENTIFIER_AUTHORITY</a>

<a href="..\ntifs\nf-ntifs-rtlsubauthoritysid.md">RtlSubAuthoritySid</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RtlInitializeSidEx routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>