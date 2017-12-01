---
UID: NC.wdm.KSYNCHRONIZE_ROUTINE
title: KSYNCHRONIZE_ROUTINE
author: windows-driver-content
description: The SynchCritSection routine is used to access hardware resources or driver data that are shared with a driver's InterruptService routine.
old-location: kernel\synchcritsection.htm
old-project: kernel
ms.assetid: 2db9b1b4-0149-4477-9f68-588c55fcbdca
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
req.alt-api: SynchCritSection
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
req.irql: Called at DIRQL (see Remarks section).
req.iface: 
req.product: Windows 10 or later.
---

# KSYNCHRONIZE_ROUTINE callback



## -description
<p>The <i>SynchCritSection</i> routine is used to access hardware resources or driver data that are shared with a driver's <a href="kernel.interruptservice">InterruptService</a> routine.</p>


## -prototype

````
KSYNCHRONIZE_ROUTINE SynchCritSection;

BOOLEAN SynchCritSection(
  _In_ PVOID SynchronizeContext
)
{ ... }
````


## -parameters
<dl>

### -param <i>SynchronizeContext</i> [in]

<dd>
<p>Caller-supplied context information, specified by the driver's call to <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>.</p>
</dd>
</dl>

## -returns
<p>If the routine's operation succeeds, the routine should return <b>TRUE</b>; otherwise, it should return <b>FALSE</b>. (Success and failure of this routine are driver-defined.) The specified return value becomes the return value for <b>KeSynchronizeExecution</b>.</p>

## -remarks
<p>Drivers must use <i>SynchCritSection</i> routines to access hardware resources or driver data that can also be accessed by an <i>InterruptService</i> routine (ISR).</p>

<p>The system calls a driver's <i>SynchCritSection</i> routine when the driver calls <a href="..\wdm\nf-wdm-kesynchronizeexecution.md">KeSynchronizeExecution</a>. When a driver calls <b>KeSynchronizeExecution</b>, it specifies the address of a <i>SynchCritSection</i> routine, context information for the routine, and an interrupt object pointer. The <b>KeSynchronizeExecution</b> routine acquires the interrupt object's spin lock, then calls the <i>SynchCritSection</i> routine.</p>

<p>A driver's <i>SynchCritSection</i> routine executes at the same IRQL as the ISR with which it is associated. Specifically, it executes at some system-assigned <a href="wdkgloss.d#wdkgloss.device_interrupt_request_level__dirql_#wdkgloss.device_interrupt_request_level__dirql_"><i>DIRQL</i></a>, as specified by the <i>SynchronizeIrql</i> parameter to <a href="..\wdm\nf-wdm-ioconnectinterrupt.md">IoConnectInterrupt</a>. (Other devices, with higher DIRQL values, can interrupt a <i>SynchCritSection</i> routine.)</p>

<p>To define a <i>SynchCritSection</i> callback routine, you must first provide a function declaration that identifies the type of callback routine you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>SynchCritSection</i> callback routine that is named <code>MySynchCritSection</code>, use the KSYNCHRONIZE_ROUTINE type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The KSYNCHRONIZE_ROUTINE function type is defined in the Wdm.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the KSYNCHRONIZE_ROUTINE function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/3260b53e-82be-4dbc-8ac5-d0e52de77f9d">Declaring Functions by Using Function Role Types for WDM Drivers</a>. For information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.</p>

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
<p>Called at DIRQL (see Remarks section).</p>
</td>
</tr>
</table>