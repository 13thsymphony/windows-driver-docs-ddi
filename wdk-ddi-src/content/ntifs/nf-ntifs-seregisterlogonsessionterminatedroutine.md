---
UID : NF:ntifs.SeRegisterLogonSessionTerminatedRoutine
title : SeRegisterLogonSessionTerminatedRoutine function
author : windows-driver-content
description : The SeRegisterLogonSessionTerminatedRoutine routine registers a callback routine to be called when a logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.
old-location : ifsk\seregisterlogonsessionterminatedroutine.htm
old-project : ifsk
ms.assetid : 6cba6db5-b91f-46f0-939e-b02693c81438
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : SeRegisterLogonSessionTerminatedRoutine
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SeRegisterLogonSessionTerminatedRoutine
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : PASSIVE_LEVEL
req.typenames : TOKEN_TYPE
---


# SeRegisterLogonSessionTerminatedRoutine function
The <b>SeRegisterLogonSessionTerminatedRoutine</b> routine registers a callback routine to be called when a logon session terminates. A logon session terminates when the last token referencing the logon session is deleted.

## Syntax

````
NTSTATUS SeRegisterLogonSessionTerminatedRoutine(
  _In_ PSE_LOGON_SESSION_TERMINATED_ROUTINE CallbackRoutine
);
````

## Parameters

`CallbackRoutine`

Address of routine to call when a logon session terminates.


## Return Value

<b>SeRegisterLogonSessionTerminatedRoutine</b> can return one of the following:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The callback routine was successfully registered.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The value of <i>CallbackRoutine</i> is <b>NULL</b>.
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>A list entry could not be allocated for the callback routine.

## Remarks

Each call to <b>SeRegisterLogonSessionTerminatedRoutine</b> must be matched by a subsequent call to <b>SeUnregisterLogonSessionTerminatedRoutine</b>.

For more information about security and access control, see the documentation on these topics in the Microsoft Windows SDK.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\ntifs\nf-ntifs-seunregisterlogonsessionterminatedroutine.md">SeUnregisterLogonSessionTerminatedRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20SeRegisterLogonSessionTerminatedRoutine routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>