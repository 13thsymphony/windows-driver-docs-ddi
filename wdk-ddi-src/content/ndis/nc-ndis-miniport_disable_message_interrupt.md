---
UID: NC.ndis.MINIPORT_DISABLE_MESSAGE_INTERRUPT
title: MINIPORT_DISABLE_MESSAGE_INTERRUPT
author: windows-driver-content
description: NDIS can call a miniport driver's MiniportDisableMessageInterrupt handler to disable a message interrupt for diagnostic and troubleshooting purposes.
old-location: netvista\miniportdisablemessageinterrupt.htm
old-project: netvista
ms.assetid: 68d2076d-c991-4219-b6c3-2399ff5c11a3
ms.author: windowsdriverdev
ms.date: 12/8/2017
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
req.alt-api: MiniportDisableMessageInterrupt
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
req.irql: DIRQL (see Remarks section)
---

# MINIPORT_DISABLE_MESSAGE_INTERRUPT callback



## -description
NDIS can call a miniport driver's 
   <i>MiniportDisableMessageInterrupt</i> handler to disable a message interrupt for diagnostic and
   troubleshooting purposes.



## -prototype

````
MINIPORT_DISABLE_MESSAGE_INTERRUPT MiniportDisableMessageInterrupt;

VOID MiniportDisableMessageInterrupt(
  _In_ NDIS_HANDLE MiniportInterruptContext,
  _In_ ULONG       MessageId
)
{ ... }
````


## -parameters

### -param MiniportInterruptContext [in]

A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="netvista.ndismregisterinterruptex">
     NdisMRegisterInterruptEx</a> function.


### -param MessageId [in]

A message-signaled interrupt. 
     <i>MessageId</i> is an index to the 
     <a href="kernel.io_interrupt_message_info_entry">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="kernel.io_interrupt_message_info">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


## -returns
None


## -remarks
A miniport driver must provide a
    <i>MiniportDisableMessageInterrupt</i> function if the driver calls the 
    <a href="netvista.ndismregisterinterruptex">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable a message interrupt as explained in the 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a> and 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
    MiniportMessageInterruptDpc</a> reference pages.

NDIS calls the 
    <a href="..\ndis\nc-ndis-miniport_enable_message_interrupt.md">
    MiniportEnableMessageInterrupt</a> and 
    <i>MiniportDisableMessageInterrupt</i> functions to enable and disable interrupts for diagnostic and
    troubleshooting purposes. Typically, 
    <i>MiniportEnableMessageInterrupt</i> and 
    <i>MiniportDisableMessageInterrupt</i> access miniport driver resources that are shared by the 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt.md">
    MiniportMessageInterrupt</a> function. Therefore, NDIS calls these handlers at DIRQL.

To define a <i>MiniportDisableMessageInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportDisableMessageInterrupt</i> function that is named "MyDisableMessageInterrupt", use the <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_DISABLE_MESSAGE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
DIRQL (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_interrupt_message_info">IO_INTERRUPT_MESSAGE_INFO</a>
</dt>
<dt>
<a href="kernel.io_interrupt_message_info_entry">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_enable_message_interrupt.md">
   MiniportEnableMessageInterrupt</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>
</dt>
<dt>
<a href="netvista.ndis_miniport_interrupt_characteristics">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>
</dt>
<dt>
<a href="netvista.ndismregisterinterruptex">NdisMRegisterInterruptEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_DISABLE_MESSAGE_INTERRUPT callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

