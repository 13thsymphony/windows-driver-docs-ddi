---
UID: NC.ndis.MINIPORT_ISR
title: MINIPORT_ISR
author: windows-driver-content
description: NDIS calls the MiniportInterrupt function when a NIC, or another device that shares the interrupt with the NIC, generates an interrupt.
old-location: netvista\miniportinterrupt.htm
old-project: netvista
ms.assetid: 810503b9-75cd-4b38-ab1f-de240968ded6
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: RxNameCacheInitialize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MiniportInterrupt
req.alt-loc: Ndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section
req.iface: 
---

# MINIPORT_ISR callback



## -description
<p>NDIS calls the
   <i>MiniportInterrupt</i> function when a NIC, or another device that shares the
   interrupt with the NIC, generates an interrupt.</p>


## -prototype

````
MINIPORT_ISR MiniportInterrupt;

BOOLEAN MiniportInterrupt(
  _In_  NDIS_HANDLE MiniportInterruptContext,
  _Out_ PBOOLEAN    QueueDefaultInterruptDpc,
  _Out_ PULONG      TargetProcessors
)
{ ... }
````


## -parameters
<dl>

### -param <i>MiniportInterruptContext</i> [in]

<dd>
<p>A handle to a block of interrupt context information. The miniport driver supplied this handle in
     the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.</p>
</dd>

### -param <i>QueueDefaultInterruptDpc</i> [out]

<dd>
<p>A pointer to a BOOLEAN variable that the miniport driver sets before it returns from this call. A
     miniport driver sets this value to <b>TRUE</b> to indicate that the driver requires a DPC on the default
     (current) CPU. If this value is set to <b>TRUE</b>, NDIS ignores the value of the 
     <i>TargetProcessors</i> parameter. If it is  set to <b>FALSE</b>, NDIS uses the value of the 
     <i>TargetProcessors</i> parameter to schedule DPCs. If 
     <i>QueueDefaultInterruptDpc</i> is <b>TRUE</b>, NDIS will schedule a DPC regardless of the
     return value from 
     <i>MiniportInterrupt</i>.</p>
</dd>

### -param <i>TargetProcessors</i> [out]

<dd>
<p>A bitmask that indicates the target processors for which NDIS should schedule a DPC. This bitmask represents the first 32 processors in processor group 0. Each bit in 
     the bitmask identifies a CPU. If the caller sets bit 0, NDIS schedules a DPC for CPU 0. If the caller sets bit 1, NDIS
     schedules a DPC for CPU 1, and so on. If 
     <i>QueueDefaultInterruptDpc</i> is set to <b>FALSE</b> and 
     <i>TargetProcessors</i> is set to zero, NDIS will not schedule any DPCs. Otherwise,
     NDIS will schedule DPCs regardless of the return value from 
     <i>MiniportInterrupt</i>.</p>
<div class="alert"><b>Note</b>  NDIS
     6.20 and later drivers should not use this parameter to schedule DPCs. Instead, they should set this parameter to zero and use the 
     <a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a> function to schedule DPCs.</div>
<div> </div>
</dd>
</dl>

## -returns
<p><i>MiniportInterrupt</i> returns one of the following values:</p><dl>
<dt><b><b>TRUE</b></b></dt>
</dl><p>
<a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a> determined that the underlying NIC generated the
       interrupt.</p><dl>
<dt><b><b>FALSE</b></b></dt>
</dl><p>
<a href="..\ndis\nc-ndis-miniport-isr.md">MiniportInterrupt</a> determined that the underlying NIC did not generate the
       interrupt.</p>

<p> </p>

## -remarks
<p>Miniport drivers that register an interrupt with the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    must provide a 
    <i>MiniportInterrupt</i> function.</p>

<p>A miniport driver should do as little work as possible in its 
    <i>MiniportInterrupt</i> function. It should defer I/O operations for the interrupts
    that the NIC generates to the 
    <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a> function.</p>

<p>When an interrupt occurs on a NIC's interrupt line, NDIS calls the miniport driver's 
    <i>MiniportInterrupt</i> function.</p>

<p>All NICs can share line-based interrupts with other devices on the I/O bus. If the NIC did not
    generate the interrupt, 
    <i>MiniportInterrupt</i> should return <b>FALSE</b> immediately so that the system can call
    the driver of the device that generated the interrupt. If the 
    <i>QueueDefaultInterruptDpc</i> is set to <b>FALSE</b> and the 
    <i>TargetProcessors</i> parameter is set to zero, NDIS will not schedule any DPCs.
    Otherwise, NDIS will schedule DPCs egardless of the re<i>MiniportInterrupt</i>turn value from 
    <i>MiniportInterrupt</i>.</p>

<p>If the interrupt is for the NIC,
     <i>MiniportInterrupt</i> dismisses the interrupt on the NIC, saves whatever state it
    must about the interrupt, and defers as much of the I/O processing as possible to the 
    <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a> function.</p>

<p>If the underlying NIC generated the specified interrupt and the miniport driver will request deferred
    procedure calls (DPCs), the miniport driver should disable all further interrupts from the NIC and
    reenable the interrupts after all the DPCs are finished.</p>

<p>The miniport driver should set 
    <i>QueueDefaultInterruptDpc</i> to <b>TRUE</b> to schedule a DPC for the default CPU only.
    The driver could do this, for example, if:</p>

<p>The NIC generated the interrupt to signal the completion of a send operation, or any other request
      that doesn't run on other CPUs.</p>

<p>The NIC generated the interrupt to signal received data and the miniport driver cannot process
      received packets in separate DPCs.</p>

<p>The interrupt indicates received packets and the miniport driver can process received packets in
      separate DPCs, but <a href="netvista.ndis_receive_side_scaling2">receive side scaling (RSS)</a> is not enabled for the miniport driver. For more information,
      see 
      <a href="netvista.oid_gen_receive_scale_capabilities">
      OID_GEN_RECEIVE_SCALE_CAPABILITIES</a> and 
      <a href="netvista.oid_gen_receive_scale_parameters">
      OID_GEN_RECEIVE_SCALE_PARAMETERS</a>.</p>

<p>If a miniport driver processes received packets in separate DPCs, the driver sets the 
    <i>QueueDefaultInterruptDpc</i> parameter to <b>FALSE</b>. The miniport driver should set the
    
    <i>TargetProcessors</i> bit for the CPU that is associated with each nonempty receive
    queue. NDIS will schedule a DPC on each of the indicated CPUs.</p>

<p>If 
    <i>MiniportInterrupt</i> shares resources, such as NIC registers or state variables,
    with another 
    <i>MiniportXxx</i> function that runs at a lower IRQL, that 
    <i>MiniportXxx</i> function must call the 
    <a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
    NdisMSynchronizeWithInterruptEx</a> function. This ensures that the driver's 
    <i>MiniportSynchronizeInterrupt</i> function accesses the shared resources in a
    synchronized and multiprocessor-safe manner.</p>

<p>A miniport driver can call the 
    <a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">
    NdisMDeregisterInterruptEx</a> function from its 
    <a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a> or 
    <a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a> function to release
    resources that it allocated with 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>. After 
    <b>NdisMDeregisterInterruptEx</b> returns, NDIS does not call a miniport
    driver's 
    <i>MiniportInterrupt</i> or 
    <a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a> function.</p>

<p>NDIS calls 
    <i>MiniportInterrupt</i> at the DIRQL of the interrupt that the miniport driver
    registered in a previous call to 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>. Therefore, 
    <i>MiniportInterrupt</i> must call the subset of the NDIS functions, such as the 
    <b>NdisRaw</b><i>Xxx</i> or 
    <b>NdisRead/WriteRegister</b><i>Xxx</i> functions, that are safe to call at any IRQL.</p>

<p>To define a <i>MiniportInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="NULL">Code Analysis for Drivers</a>, <a href="NULL">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.</p>

<p>For example, to define a <i>MiniportInterrupt</i> function that is named "MyInterrupt", use the <b>MINIPORT_ISR</b> type as shown in this code example:</p>

<p>Then, implement your function as follows:</p>

<p>The <b>MINIPORT_ISR</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ISR</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="NULL">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>See Remarks section</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ndis\nc-ndis-miniport-halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-interrupt-dpc.md">MiniportInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-synchronize-interrupt.md">
   MiniportSynchronizeInterrupt</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-miniport-interrupt-characteristics.md">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">NdisMDeregisterInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismqueuedpcex.md">NdisMQueueDpcEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismsynchronizewithinterruptex.md">
   NdisMSynchronizeWithInterruptEx</a>
</dt>
<dt>
<a href="netvista.oid_gen_receive_scale_capabilities">
   OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>
</dt>
<dt>
<a href="netvista.oid_gen_receive_scale_parameters">
   OID_GEN_RECEIVE_SCALE_PARAMETERS</a>
</dt>
<dt>
<a href="netvista.ndis_receive_side_scaling2">Receive Side Scaling (RSS)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ISR callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
