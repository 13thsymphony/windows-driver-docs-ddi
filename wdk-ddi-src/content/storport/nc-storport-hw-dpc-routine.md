---
UID: NC.storport.HW_DPC_ROUTINE
title: HW_DPC_ROUTINE
author: windows-driver-content
description: The HwStorDpcRoutine routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism.
old-location: storage\hwstordpcroutine.htm
old-project: storage
ms.assetid: bc646191-e405-49e2-8793-0c0b81e52f50
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: STORAGE_DEVICE_UNIQUE_IDENTIFIER, STORAGE_DEVICE_UNIQUE_IDENTIFIER, *PSTORAGE_DEVICE_UNIQUE_IDENTIFIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: HwStorDpcRoutine
req.alt-loc: Storport.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section.)
req.iface: 
req.product: Windows 10 or later.
---

# HW_DPC_ROUTINE callback



## -description
<p>The <b>HwStorDpcRoutine</b> routine is a routine that is deferred for execution at DISPATCH IRQL by means of the deferred procedure call (DPC) mechanism. </p>


## -prototype

````
HW_DPC_ROUTINE HwStorDpcRoutine;

VOID HwStorDpcRoutine(
   IN PSTOR_DPC Dpc,
   IN PVOID     HwDeviceExtension,
   IN PVOID     SystemArgument1,
   IN PVOID     SystemArgument2
)
{ ... }
````


## -parameters
<dl>

### -param <i>Dpc</i> 

<dd>
<p>A pointer to a Storport DPC  context. </p>
</dd>

### -param <i>HwDeviceExtension</i> 

<dd>
<p>A pointer to the per-adapter device extension. </p>
</dd>

### -param <i>SystemArgument1</i> 

<dd>
<p>A pointer to caller-supplied information.</p>
</dd>

### -param <i>SystemArgument2</i> 

<dd>
<p>A pointer to caller-supplied information.</p>
</dd>
</dl>

## -returns
<p>None. </p>

## -remarks
<p>When a miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a> to initialize a DPC it must load the <i>HwDpcRoutine</i>  parameter of the <b>StorPortInitializeDpc</b> routine with a pointer to the <b>HwStorDpcRoutine</b> routine. </p>

<p>Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine or with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557403">HwStorInterrupt</a> routine by acquiring the appropriate spin lock with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>. For more information about the management of spin locks within DPC routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567116">StorPortIssueDpc</a>. </p>

<p>The name <b>HwStorDpcRoutine</b> is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:</p>

<p>The port driver calls the <b>HwStorDpcRoutine</b> routine at DISPATCH IRQL.</p>

<p>To define an <b>HwStorDpcRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p> For example, to define a <b>HwStorDpcRoutine</b> callback routine that is named <i>MyHwDpcRoutine</i>, use the <b>HW_DPC_ROUTINE</b> type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The <b>HW_DPC_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_DPC_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

<p>When a miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a> to initialize a DPC it must load the <i>HwDpcRoutine</i>  parameter of the <b>StorPortInitializeDpc</b> routine with a pointer to the <b>HwStorDpcRoutine</b> routine. </p>

<p>Any particular instance of a DPC routine is guaranteed to be synchronized with other instances of the DPC routine. A DPC routine can synchronize itself with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a> routine or with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557403">HwStorInterrupt</a> routine by acquiring the appropriate spin lock with a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>. For more information about the management of spin locks within DPC routines, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff567116">StorPortIssueDpc</a>. </p>

<p>The name <b>HwStorDpcRoutine</b> is just a placeholder. The actual prototype of this routine is defined in <i>storport.h</i> as follows:</p>

<p>The port driver calls the <b>HwStorDpcRoutine</b> routine at DISPATCH IRQL.</p>

<p>To define an <b>HwStorDpcRoutine</b> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.</p>

<p> For example, to define a <b>HwStorDpcRoutine</b> callback routine that is named <i>MyHwDpcRoutine</i>, use the <b>HW_DPC_ROUTINE</b> type as shown in this code example:</p>

<p>Then, implement your callback routine as follows:</p>

<p>The <b>HW_DPC_ROUTINE</b> function type is defined in the Storport.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>HW_DPC_ROUTINE</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/40BD11CD-A559-4F90-BF39-4ED2FB800392">Declaring Functions Using Function Role Types for Storport Drivers</a>. For information about _Use_decl_annotations_, see <a href="c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Storport.h (include Storport.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>DISPATCH_LEVEL (See Remarks section.)</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557403">HwStorInterrupt</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557423">HwStorStartIo</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567025">StorPortAcquireSpinLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567110">StorPortInitializeDpc</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff567116">StorPortIssueDpc</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HwStorDpcRoutine routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
