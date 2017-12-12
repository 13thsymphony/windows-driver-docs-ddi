---
UID: NF.wdm.DbgPrint
title: DbgPrint function
author: windows-driver-content
description: The DbgPrint routine sends a message to the kernel debugger.
old-location: devtest\dbgprint.htm
old-project: devtest
ms.assetid: abff1656-dceb-464f-a89c-30d7a24f742d
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: DbgPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DbgPrint
req.alt-loc: NtDll.dll,NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtDll.lib (user mode); NtosKrnl.lib (kernel mode)
req.dll: NtDll.dll (user mode); NtosKrnl.exe (kernel mode)
req.irql: <= DIRQL (see Comments section)
req.product: Windows 10 or later.
---

# DbgPrint function



## -description
The <b>DbgPrint</b> routine sends a message to the kernel debugger. 

 In Windows Vista and later versions of Windows, <b>DbgPrint</b> sends a message only when the conditions that you specify apply (see the <a href="#remarks"><b>Remarks</b></a> section for information).



## -syntax

````
ULONG DbgPrint(
  _In_ PCHAR Format,
             arguments
);
````


## -parameters

### -param Format [in]

Specifies a pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style <a href="http://go.microsoft.com/fwlink/p/?linkid=83949">format specification fields</a>. However, the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) can only be used with IRQL = PASSIVE_LEVEL. The <b>DbgPrint</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).


### -param arguments 

Specifies arguments for the format string, as in <b>printf</b>.


## -returns
If successful, <b>DbgPrint</b> returns the NTSTATUS code STATUS_SUCCESS; otherwise it returns the appropriate error code.


## -remarks
<b>DbgPrint</b> and <b>DbgPrintEx</b> can be called at IRQL&lt;=DIRQL. However, Unicode format codes (%wc and %ws) can be used only at IRQL=PASSIVE_LEVEL. Also, because the debugger uses interprocess interrupts (IPIs) to communicate with other processors, calling <b>DbgPrint</b> at IRQL&gt;DIRQL can cause deadlocks.

Only kernel-mode drivers can call the <b>DbgPrint</b> routine. 

In Microsoft Windows Server 2003 and earlier versions of Windows, the <b>DbgPrint</b> routine sends a message to the kernel debugger. In Windows Vista and later versions of Windows, <b>DbgPrint</b> sends a message only if certain conditions apply. Specifically, it behaves like the <a href="devtest.dbgprintex">DbgPrintEx</a> routine with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:

For more information about message filtering, components, and message importance level, see <a href="https://msdn.microsoft.com/2ad320f6-596d-4b4c-bfad-d570c856bcc7">Reading and Filtering Debugging Messages</a>.

Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>DbgPrint</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.

There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>DbgPrint</b> will only transmit 512 bytes of information. There is also a limit to the size of the DbgPrint buffer. See <a href="devtest.reading_and_filtering_debugging_messages#ddk_the_dbgprint_buffer_and_the_debugger_tools#ddk_the_dbgprint_buffer_and_the_debugger_tools">DbgPrint Buffer and the Debugger</a> for details.  


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Microsoft Windows 2000 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtDll.lib (user mode); </dt>
<dt>NtosKrnl.lib (kernel mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtDll.dll (user mode); </dt>
<dt>NtosKrnl.exe (kernel mode)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DIRQL (see Comments section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="devtest.dbgprintex">DbgPrintEx</a>
</dt>
<dt>
<a href="devtest.kdprint">KdPrint</a>
</dt>
<dt>
<a href="devtest.kdprintex">KdPrintEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20DbgPrint routine%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

