---
UID: NF:wdm.KdPrintEx
title: KdPrintEx macro
author: windows-driver-content
description: The KdPrintEx macro sends a string to the kernel debugger if the conditions you specify are met.A call to KdPrintEx requires double parentheses.
old-location: devtest\kdprintex.htm
old-project: devtest
ms.assetid: 8383e9c8-0058-47bf-9a6e-ed05e61a58f1
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: KdPrintEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows XP and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KdPrintEx
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib (See DbgPrintEx.)
req.dll: NtosKrnl.exe
req.irql: 
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KdPrintEx function
The <b>KdPrintEx</b> macro sends a string to the kernel debugger if the conditions you specify are met.

A call to <b>KdPrintEx</b> requires double parentheses.

## Syntax

````
ULONG KdPrintEx(
  _In_ ULONG ComponentId,
  _In_ ULONG Level,
  _In_ PCSTR Format,
       ...   arguments
);
````

## Parameters

`_x_`




## Return Value

None

## Remarks

<b>KdPrintEx</b> is identical to the <b>DbgPrintEx</b> routine in code that is compiled for a debug configuration. This routine has no effect in code that is compiled for a release build. Only kernel-mode drivers can call the <b>KdPrintEx</b> routine.<div class="alert"><b>Note</b>  The Windows Driver Kit (WDK) 8 and WDK 7 manage the <b>DBG</b> preprocessor constant define appropriately for debug (check) and release (free) builds. For more information, see <a href="https://msdn.microsoft.com/7879b6c6-4985-4817-a8bc-b287397df721">Conditional Compilation and the Build Environment</a>.</div>
<div> </div>


<b>KdPrintEx</b> either passes the specified string to the kernel debugger or does nothing at all, depending on the values of <i>ComponentId</i>, <i>Level</i>, and the corresponding component filter masks. For details, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>KdPrintEx</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>KdPrintEx</b> will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See <a href="devtest.reading_and_filtering_debugging_messages#ddk_the_dbgprint_buffer_and_the_debugger_tools#ddk_the_dbgprint_buffer_and_the_debugger_tools">The DbgPrint Buffer and the Debugger</a> for details.

This routine is defined in ntddk.h and ndis.h; component filter IDs are defined in dpfilter.h, ndis.h, and wdm.h. Include ntddk.h or ndis.h.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Microsoft Windows XP and later. Available in Microsoft Windows XP and later. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h) |
| **Library** | NtosKrnl.lib (See DbgPrintEx.) |
| **DLL** | NtosKrnl.exe |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-dbgprint.md">DbgPrint</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-dbgprintex.md">DbgPrintEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kdprint.md">KdPrint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20KdPrintEx function%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>