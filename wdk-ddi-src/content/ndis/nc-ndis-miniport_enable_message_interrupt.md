---
UID: NC:ndis.MINIPORT_ENABLE_MESSAGE_INTERRUPT
title: MINIPORT_ENABLE_MESSAGE_INTERRUPT
author: windows-driver-content
description: NDIS can call a miniport driver's MiniportEnableMessageInterrupt function to enable a message interrupt for diagnostic and troubleshooting purposes.
old-location: netvista\miniportenablemessageinterrupt.htm
old-project: netvista
ms.assetid: b0e1bbef-8116-4455-aa5c-7f47386a3700
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_ENABLE_MESSAGE_INTERRUPT, MiniportEnableMessageInterrupt, MiniportEnableMessageInterrupt callback function [Network Drivers Starting with Windows Vista], ndis/MiniportEnableMessageInterrupt, ndis_interrupts_miniport_functions_ref_cc88ce4b-e75b-4da8-89aa-3d449451a0d3.xml, netvista.miniportenablemessageinterrupt
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndis.h
api_name:
-	MiniportEnableMessageInterrupt
product: Windows
targetos: Windows
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---


# MINIPORT_ENABLE_MESSAGE_INTERRUPT callback function
NDIS can call a miniport driver's 
   <i>MiniportEnableMessageInterrupt</i> function to enable a message interrupt for diagnostic and
   troubleshooting purposes.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> type.
   For more information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_ENABLE_MESSAGE_INTERRUPT MiniportEnableMessageInterrupt;

void MiniportEnableMessageInterrupt(
  NDIS_HANDLE MiniportInterruptContext,
  ULONG MessageId
)
{...}
```

## Parameters

`MiniportInterruptContext`

A handle to a block of context information. The miniport driver supplied this handle in the 
     <i>MiniportInterruptContext</i> parameter that the miniport driver passed to the 
     <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">
     NdisMRegisterInterruptEx</a> function.

`MessageId`

A message-signaled interrupt. 
     <i>MessageId</i> is an index to the 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
     IO_INTERRUPT_MESSAGE_INFO_ENTRY</a> structures inside a 
     <a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">
     IO_INTERRUPT_MESSAGE_INFO</a> structure. NDIS passes a pointer to the associated
     IO_INTERRUPT_MESSAGE_INFO structure at the 
     <b>MessageInfoTable</b> member when the driver successfully registers for MSI with the 
     <b>NdisMRegisterInterruptEx</b> function.


## Return Value

None

## Remarks

A miniport driver must provide a
    <i>MiniportEnableMessageInterrupt</i> function if the driver calls the 
    <a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a> function
    to register an interrupt.

Miniport drivers should disable and enable a message interrupt as explained in the 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a> and 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">
    MiniportMessageInterruptDpc</a> reference pages.

NDIS calls the 
    <i>MiniportEnableMessageInterrupt</i> and 
    <a href="..\ndis\nc-ndis-miniport_disable_message_interrupt.md">
    MiniportDisableMessageInterrupt</a> functions to enable and disable a message interrupt for diagnostic
    and troubleshooting purposes. Typically, 
    <i>MiniportEnableMessageInterrupt</i> and 
    <i>MiniportDisableMessageInterrupt</i> access miniport driver resources that are shared by the 
    <a href="..\ndis\nc-ndis-miniport_message_interrupt.md">
    MiniportMessageInterrupt</a> function. Therefore, NDIS calls these handlers at DIRQL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportEnableMessageInterrupt</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportEnableMessageInterrupt</i> function that is named "MyEnableMessageInterrupt", use the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_ENABLE_MESSAGE_INTERRUPT MyEnableMessageInterrupt;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyEnableMessageInterrupt(
    __in  NDIS_HANDLE  MiniportInterruptContext,
    __in  ULONG  MessageId
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_ENABLE_MESSAGE_INTERRUPT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Windows |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | DIRQL (see Remarks section) |

## See Also

<a href="..\wdm\ns-wdm-_io_interrupt_message_info.md">IO_INTERRUPT_MESSAGE_INFO</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_interrupt_characteristics.md">
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</a>



<a href="..\ndis\nf-ndis-ndismregisterinterruptex.md">NdisMRegisterInterruptEx</a>



<a href="..\wdm\ns-wdm-_io_interrupt_message_info_entry.md">
   IO_INTERRUPT_MESSAGE_INFO_ENTRY</a>



<a href="..\ndis\nc-ndis-miniport_disable_message_interrupt.md">
   MiniportDisableMessageInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_ENABLE_MESSAGE_INTERRUPT callback function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>