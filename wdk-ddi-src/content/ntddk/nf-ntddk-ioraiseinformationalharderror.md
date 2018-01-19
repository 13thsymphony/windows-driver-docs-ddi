---
UID : NF:ntddk.IoRaiseInformationalHardError
title : IoRaiseInformationalHardError function
author : windows-driver-content
description : The IoRaiseInformationalHardError routine sends a dialog box to the user, warning about a device I/O error that indicates why a user I/O request failed.
old-location : kernel\ioraiseinformationalharderror.htm
old-project : kernel
ms.assetid : 14e9a28c-65cc-4e90-8220-85f1981c8cd7
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : IoRaiseInformationalHardError
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ntddk.h
req.include-header : Ntddk.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IoRaiseInformationalHardError
req.alt-loc : NtosKrnl.exe
req.ddi-compliance : IrqlIoApcLte, HwStorPortProhibitedDDIs
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <=APC_LEVEL
req.typenames : WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---


# IoRaiseInformationalHardError function
The <b>IoRaiseInformationalHardError</b> routine sends a dialog box to the user, warning about a device I/O error that indicates why a user I/O request failed.

## Syntax

````
BOOLEAN IoRaiseInformationalHardError(
  _In_     NTSTATUS        ErrorStatus,
  _In_opt_ PUNICODE_STRING String,
  _In_opt_ PKTHREAD        Thread
);
````

## Parameters

`ErrorStatus`

The error status code (IO_ERR_<i>XXX</i>).

`String`

A pointer to a Unicode string, which provides additional information about the error. Some NT status codes require a string parameter, such as a file or directory name. If the specified <i>ErrorStatus</i> value does not require a string parameter, set <i>String</i> to <b>NULL</b>.

`Thread`

A pointer to the thread whose IRP was failed due to the error specified by the <i>ErrorStatus</i> parameter.


## Return Value

<b>IoRaiseInformationalHardError</b> returns <b>TRUE</b> if the dialog box was successfully queued. This routine returns <b>FALSE</b> if dialog boxes are disabled for <i>Thread</i>, a pool allocation failed, too many dialog boxes are already queued, or an equivalent dialog box is already pending a user response (such as waiting for the user to press RETURN).

## Remarks

<b>IoRaiseInformationalHardError</b> takes a system-defined NT error value as a parameter. Driver writers can use the event log APIs to communicate driver-defined event strings to the user.

<b>IoRaiseInformationalHardError</b> behaves as follows:

If a previous call to the <a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a> routine disabled hard errors for the specified thread, <b>IoRaiseInformationalHardError</b> returns <b>FALSE</b>.

Starting with Windows Vista, if the routine is called from a thread in session 0 (that is, from any system thread), no dialog box appears when the routine succeeds and returns <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddk.h (include Ntddk.h) |
| **Library** |  |
| **IRQL** | <=APC_LEVEL |
| **DDI compliance rules** | IrqlIoApcLte, HwStorPortProhibitedDDIs |

## See Also

<dl>
<dt>
<a href="..\ntddk\nf-ntddk-iosetharderrororverifydevice.md">IoSetHardErrorOrVerifyDevice</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-iosetthreadharderrormode.md">IoSetThreadHardErrorMode</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-psgetcurrentthread.md">PsGetCurrentThread</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoRaiseInformationalHardError routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>