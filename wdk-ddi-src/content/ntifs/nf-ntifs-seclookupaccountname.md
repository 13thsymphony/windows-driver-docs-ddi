---
UID : NF:ntifs.SecLookupAccountName
title : SecLookupAccountName function
author : windows-driver-content
description : SecLookupAccountName accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.
old-location : ifsk\seclookupaccountname.htm
old-project : ifsk
ms.assetid : 5b1c3cc4-6185-4299-86ed-662a2b445042
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ksecddref_1f4959e5-ea3b-440d-af1b-df05782eefce.xml, ifsk.seclookupaccountname, ntifs/SecLookupAccountName, SecLookupAccountName function [Installable File System Drivers], SecLookupAccountName
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : The SecLookupAccountName function is only available on Windows XP and later.
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
req.lib : Ksecdd.lib
req.dll : 
req.irql : <= APC_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : TOKEN_TYPE
---


# SecLookupAccountName function
<b>SecLookupAccountName</b> accepts an account as input and retrieves a security identifier (SID) for the account and the name of the domain on which the account was found.

## Syntax

````
NTSTATUS SecLookupAccountName(
  _In_    PUNICODE_STRING Name,
  _Inout_ PULONG          SidSize,
  _Out_   PSID            Sid,
  _Out_   PSID_NAME_USE   NameUse,
  _Out_   PULONG          DomainSize,
  _Inout_ PUNICODE_STRING ReferencedDomain
);
````

## Parameters

`Name`

A pointer to a Unicode string that specifies the account name. Use a fully qualified string in the domain_name\user_name format to ensure that <b>SecLookupAccountName</b> finds the account in the desired domain.

`SidSize`

A pointer to a variable that specifies the size of the <i>Sid</i> buffer. On input, this value specifies the size in bytes of the input <i>Sid</i> buffer. If the function fails because the buffer is too small or if <i>SidSize</i> is zero, this variable receives the required buffer size. On success, this variable contains the size of the returned <i>Sid</i>.

`Sid`

A pointer to a buffer that receives the SID structure that corresponds to the account name pointed to by the <i>Name</i> parameter. If this parameter is <b>NULL</b>, <i>SidSize</i> must be zero.

`NameUse`

A pointer to a SID_NAME_USE enumerated type that indicates the type of the account when the function returns.

`OPTIONAL`

TBD

`OPTIONAL`

TBD


## Return Value

<b>SecLookupAccountName</b> returns STATUS_SUCCESS on success or one of the following error codes on failure: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>SEC_E_INTERNAL_ERROR</b></dt>
</dl>
</td>
<td width="60%">
An internal error occurred while trying to connect to the Local System Authority (LSA) or the local procedure call (LPC) to the security provider failed. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
The process ID associated with the currently executing thread does not match the current process ID. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The buffer size for the <i>Sid</i> or the <i>ReferencedDomain</i> parameter was too small.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The length of the <i>Name</i> parameter exceeded the length allowed in a message to the Local System Authority. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NONE_MAPPED</b></dt>
</dl>
</td>
<td width="60%">
The <i>Name</i> parameter could not be found. 

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_PROCESS_IS_TERMINATING</b></dt>
</dl>
</td>
<td width="60%">
This process has terminated so it is not possible to establish the local procedure call (LPC) connection.

</td>
</tr>
</table>

## Remarks

<b>SecLookupAccountName</b> attempts to find a SID for the specified name. The function checks built-in and administratively defined local accounts. Next, the function checks the primary domain. If the name is not found there, trusted domains are checked.

Use fully qualified account names (for example, domain_name\user_name) instead of isolated names (for example, user_name). Fully qualified names are unambiguous and provide better performance when the lookup is performed. This function also supports fully qualified DNS names (for example, example.example.com\user_name) and user principal names (UPN) (for example, someone@example.com).

In addition to looking up local accounts, local domain accounts, and explicitly trusted domain accounts, <b>SecLookupAccountName</b> can look up the name for any account in any domain in the forest.

<b>SecLookupAccountName</b> is equivalent to the Win32 <b>LookupAccountName</b> function. 

<b>SecLookupAccountName</b> is exported by the ksecdd driver, which implements this function by using user-mode helper services. Accordingly, the use of this function within file systems must obey the usual rules for communication with user-mode services. <b>SecLookupAccountName</b> cannot be used during paging file I/O.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\ntifs\nf-ntifs-seclookupaccountsid.md">SecLookupAccountSid</a>

<a href="..\ntifs\ns-ntifs-_sid.md">SID</a>

<a href="..\ntifs\nf-ntifs-seclookupwellknownsid.md">SecLookupWellKnownSid</a>

<a href="..\ntifs\ne-ntifs-_sid_name_use.md">SID_NAME_USE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SecLookupAccountName function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>