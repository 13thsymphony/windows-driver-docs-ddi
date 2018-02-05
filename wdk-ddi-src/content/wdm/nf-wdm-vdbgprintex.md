---
UID : NF:wdm.vDbgPrintEx
title : vDbgPrintEx function
author : windows-driver-content
description : The vDbgPrintEx routine sends a string to the kernel debugger if certain conditions are met.
old-location : devtest\vdbgprintex.htm
old-project : devtest
ms.assetid : e7118f5b-819f-428f-a5e6-80a36705d626
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : vDbgPrintEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Dpfilter.h, Wdm.h, Ntddk.h, Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Available in Microsoft Windows XP and later operating system versions.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : vDbgPrintEx
req.alt-loc : NtDll.dll,NtosKrnl.exe
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll : NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql : <= DIRQL (see Comments section)
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# vDbgPrintEx function
The <b>vDbgPrintEx</b> routine sends a string to the kernel debugger if certain conditions are met.

## Syntax

````
ULONG vDbgPrintEx(
  _In_ ULONG   ComponentId,
  _In_ ULONG   Level,
  _In_ PCCH    Format,
  _In_ va_list arglist
);
````

## Parameters

`ComponentId`

The component that is calling this routine. This parameter must be one of the component name filter IDs that are defined in Dpfilter.h. To avoid mixing your driver's output with the output of Windows components, you should use only the following values for <i>ComponentId</i>:

<ul>
<li>
DPFLTR_IHVVIDEO_ID 

</li>
<li>
DPFLTR_IHVAUDIO_ID 

</li>
<li>
DPFLTR_IHVNETWORK_ID 

</li>
<li>
DPFLTR_IHVSTREAMING_ID 

</li>
<li>
DPFLTR_IHVBUS_ID 

</li>
<li>
DPFLTR_IHVDRIVER_ID 

</li>
</ul>

`Level`

The severity of the message that is being sent. This parameter can be any 32-bit integer. Values between 0 and 31 (inclusive) are treated differently than values between 32 and 0xFFFFFFFF. For more information about how the values are treated, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

`Format`

A pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style formatting codes. However, you can use the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) only with IRQL = PASSIVE_LEVEL. The <b>vDbgPrintEx</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).

`arglist`

An argument list for the format string. The <b>vDbgPrintEx</b> routine uses this list in the same way that <b>vprintf</b> does.


## Return Value

<b>vDbgPrintEx</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this routine returns the appropriate error code.

## Remarks

Only kernel-mode drivers can call the <b>vDbgPrintEx</b> routine.

<b>vDbgPrintEx</b> can be called at IRQL &lt;= DIRQL. However, you can use Unicode format codes (%<b>wc</b> and %<b>ws</b>) only at IRQL = PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling <b>vDbgPrintEx</b> at IRQL &gt; DIRQL can cause deadlocks.

<b>vDbgPrintEx</b> either passes the string that it creates to the kernel debugger or does nothing at all, depending on the values of <i>ComponentId</i>, <i>Level</i>, and the corresponding component filter masks. For more information about what <b>vDbgPrintEx</b> does, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>vDbgPrintEx</b>. If you do use a string that you did not create, you must verify that this string is a valid format string and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments in the <i>arglist</i> list. However, any single call to <b>vDbgPrintEx</b> will transmit only 512 bytes of information. 

There is also a limit to the size of the buffer that the debugger uses. For more information about this limit, see <a href="devtest.reading_and_filtering_debugging_messages#ddk_the_dbgprint_buffer_and_the_debugger_tools#ddk_the_dbgprint_buffer_and_the_debugger_tools">The DbgPrint Buffer and the Debugger</a>.

This routine is defined in Wdm.h. Component filter IDs are defined in Dpfilter.h.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later operating system versions. Available in Microsoft Windows XP and later operating system versions. |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Dpfilter.h, Wdm.h, Ntddk.h, Ndis.h) |
| **Library** | NtDll.lib (user mode); NtosKrnl.lib (kernel mode) |
| **DLL** | NtDll.dll (user mode); NtosKrnl.exe (kernel mode) |
| **IRQL** | <= DIRQL (see Comments section) |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-dbgprintex.md">DbgPrintEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20vDbgPrintEx routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>