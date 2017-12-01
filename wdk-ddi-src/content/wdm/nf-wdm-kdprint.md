---
UID: NF.wdm.KdPrint
title: KdPrint
author: windows-driver-content
description: The KdPrint macro sends a message to the kernel debugger.
old-location: devtest\kdprint.htm
old-project: devtest
ms.assetid: 4a2ab12b-ee89-462d-821a-0a2db20cc36c
ms.author: windowsdriverdev
ms.date: 11/21/2017
ms.keywords: KdPrint
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KdPrint
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib (See DbgPrint.)
req.dll: NtosKrnl.exe
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# KdPrint function



## -description
<p>The <b>KdPrint</b> macro sends a message to the kernel debugger. </p>
<p>In Windows Vista and later versions of Windows, <b>KdPrint</b> sends a message only if the conditions you specify apply (see the <a href="#remarks"><b>Remarks</b></a> section for information).</p>
<p>A call to <b>KdPrint</b> requires double parentheses.</p>


## -syntax

````
ULONG KdPrint(
  _In_ PCHAR Format,
             arguments
);
````


## -parameters
<dl>

### -param <i>Format</i> [in]

<dd>
<p>Specifies a pointer to the format string to print. The <i>Format</i> string supports most of the <b>printf</b>-style <a href="http://go.microsoft.com/fwlink/p/?linkid=83949">format specification fields</a>. However, the Unicode format codes (<b>%C</b>, <b>%S</b>, <b>%lc</b>, <b>%ls</b>, <b>%wc</b>, <b>%ws</b>, and <b>%wZ</b>) can only be used with IRQL = PASSIVE_LEVEL. The <b>KdPrint</b> routine does not support any of the floating point types (<b>%f</b>, <b>%e</b>, <b>%E</b>, <b>%g</b>, <b>%G</b>, <b>%a</b>, or <b>%A</b>).</p>
</dd>

### -param <i>arguments</i> 

<dd>
<p>Specifies arguments for the format string, as in <b>printf</b>.</p>
</dd>
</dl>

## -returns
<p>If successful, <b>KdPrint</b> returns the NTSTATUS code STATUS_SUCCESS; otherwise it returns the appropriate error code.</p>

## -remarks
<p><b>KdPrint</b> is identical to the <b>DbgPrint</b> routine in code that is compiled for a debug configuration.  This routine has no effect if compiled for a release configuration. Only kernel-mode drivers can call the <b>KdPrint</b> routine.</p>

<p>In Microsoft Windows Server 2003 and earlier versions of Windows, the <b>DbgPrint</b> routine sends a message to the kernel debugger. In Windows Vista and later versions of Windows, <b>KdPrint</b> sends a message only if certain conditions apply. Specifically, it behaves like <a href="..\wdm\nf-wdm-kdprintex.md">KdPrintEx</a> with the DEFAULT component and a message importance level of DPFLTR_INFO_LEVEL. In other words, the following two function calls are identical:</p>

<p>For more information about message filtering, components, and message importance level, see <a href="NULL">Reading and Filtering Debugging Messages</a>.</p>

<p>Unless it is absolutely necessary, you should not obtain a string from user input or another process and pass it to <b>KdPrint</b>. If you do use a string that you did not create, you must verify that this is a valid format string, and that the format codes match the argument list in type and quantity. The best coding practice is for all <i>Format</i> strings to be static and defined at compile time.</p>

<p>There is no upper limit to the size of the <i>Format</i> string or the number of arguments. However, any single call to <b>KdPrint</b> will only transmit 512 bytes of information. There is also a limit to the size of the <a href="..\wdm\nf-wdm-dbgprint.md">DbgPrint</a> buffer. See <a href="devtest.reading_and_filtering_debugging_messages#ddk_the_dbgprint_buffer_and_the_debugger_tools#ddk_the_dbgprint_buffer_and_the_debugger_tools">The DbgPrint Buffer and the Debugger</a> for details.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Microsoft Windows 2000 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib (See <a href="..\wdm\nf-wdm-dbgprint.md">DbgPrint</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-dbgprint.md">DbgPrint</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-dbgprintex.md">DbgPrintEx</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-kdprintex.md">KdPrintEx</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [devtest\devtest]:%20KdPrint function%20 RELEASE:%20(11/21/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
