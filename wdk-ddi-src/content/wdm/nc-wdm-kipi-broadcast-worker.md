---
UID: NC.wdm.KIPI_BROADCAST_WORKER
title: KIPI_BROADCAST_WORKER
author: windows-driver-content
description: The IpiGenericCall routine runs simultaneously on all processors.
old-location: kernel\ipigenericcall.htm
old-project: kernel
ms.assetid: 7c4e3d6b-e000-4ac4-b200-966689d05426
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IpiGenericCall
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: Called at IPI_LEVEL.
req.iface: 
req.product: Windows 10 or later.
---

# KIPI_BROADCAST_WORKER callback



## -description
<p>The <i>IpiGenericCall</i> routine runs simultaneously on all processors.</p>


## -prototype

````
KIPI_BROADCAST_WORKER IpiGenericCall;

ULONG_PTR IpiGenericCall(
  _In_ ULONG_PTR Argument
)
{ ... }
````


## -parameters
<dl>

### -param <i>Argument</i> [in]

<dd>
<p>Supplies the value that was passed to the <a href="..\wdm\nf-wdm-keipigenericcall.md">KeIpiGenericCall</a> routine that called <i>IpiGenericCall</i>.</p>
</dd>
</dl>

## -returns
<p><i>IpiGenericCall</i> returns a driver-defined value. If <i>IpiGenericCall</i> ran on the same processor that called <b>KeIpiGenericCall</b>, <b>KeIpiGenericCall</b> returns the driver-defined value that <i>IpiGenericCall</i> returns. Otherwise, the value is ignored. </p>

## -remarks
<p><i>IpiGenericCall</i> routines run at IRQL = IPI_LEVEL, which is greater than DIRQL for every device. <i>IpiGenericCall</i> routines must satisfy the same restrictions as bug check callback routines. For more information about these restrictions, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff566401">Writing a Bug Check Callback Routine</a>.</p>

<p>To define an <i>IpiGenericCall</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define an <i>IpiGenericCall</i> callback routine that is named <code>MyIpiGenericCall</code>, use the KIPI_BROADCAST_WORKER type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The KIPI_BROADCAST_WORKER function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KIPI_BROADCAST_WORKER function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>Called at IPI_LEVEL.</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-keipigenericcall.md">KeIpiGenericCall</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IpiGenericCall routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
