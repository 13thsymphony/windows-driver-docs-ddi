---
UID : NF:ndis.NdisMRegisterInterruptEx
title : NdisMRegisterInterruptEx function
author : windows-driver-content
description : NDIS miniport drivers call the NdisMRegisterInterruptEx function to register an interrupt.
old-location : netvista\ndismregisterinterruptex.htm
old-project : netvista
ms.assetid : db0b3d51-5bbb-45fb-8c45-dda8c2212b5f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ndis_interrupts_functions_ref_9a28602d-5a32-459c-92da-9d97b93f5fde.xml, netvista.ndismregisterinterruptex, NdisMRegisterInterruptEx function [Network Drivers Starting with Windows Vista], NdisMRegisterInterruptEx, ndis/NdisMRegisterInterruptEx
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Universal
req.target-min-winverclnt : Supported in NDIS 6.0 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : Init_DeRegisterInterrupt, Init_RegisterInterrupt, Irql_Interrupt_Function, NdisMDeregisterInterruptEx
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ndis.lib
req.dll : 
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMRegisterInterruptEx function
NDIS miniport drivers call the 
  <b>NdisMRegisterInterruptEx</b> function to register an interrupt.

## Syntax

````
NDIS_STATUS NdisMRegisterInterruptEx(
  _In_  NDIS_HANDLE                              MiniportAdapterHandle,
  _In_  NDIS_HANDLE                              MiniportInterruptContext,
  _In_  PNDIS_MINIPORT_INTERRUPT_CHARACTERISTICS MiniportInterruptCharacteristics,
  _Out_ PNDIS_HANDLE                             NdisInterruptHandle
);
````

## Parameters

`MiniportAdapterHandle`

The miniport adapter handle that NDIS passed to the 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.

`MiniportInterruptContext`

A pointer to a block of context information. The miniport driver allocates this memory to store
     information about the interrupt. NDIS passes the context information block in subsequent calls to other
     functions that are associated with the interrupt.

`MiniportInterruptCharacteristics`

A pointer to an 
     <mshelp:link keywords="netvista.ndis_miniport_interrupt_characteristics" tabindex="0"><b>
     NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</b></mshelp:link> structure that the miniport driver created. The driver
     initializes this structure with handler entry points and configuration parameters that define the
     interrupt characteristics.

`NdisInterruptHandle`

A pointer to an NDIS handle. NDIS writes the handle for the newly created interrupt object to the
     address that the 
     <i>NdisInterruptHandle</i> pointer specifies.


## Return Value

<b>NdisMRegisterInterruptEx</b> can return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
NDIS initialized the interrupt object and supplied a valid interrupt handle at 
       <i>NdisInterruptHandle</i> . NDIS claimed hardware resources and set up the functions that it calls
       when an interrupt occurs.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>NdisMRegisterInterruptEx</b> failed due to insufficient resources.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>NDIS_STATUS_<i>XXX</i> or NT_STATUS_<i>XXX</i></b></dt>
</dl>
</td>
<td width="60%">
The attempt to initialize the interrupt object failed for reasons other than those in the
       preceding list.

</td>
</tr>
</table>

## Remarks

A miniport driver must call 
    <b>NdisMRegisterInterruptEx</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function if
    it manages a NIC that generates interrupts.

<i>MiniportInitializeEx</i> must call the 
    <mshelp:link keywords="netvista.ndismsetminiportattributes" tabindex="0"><b>
    NdisMSetMiniportAttributes</b></mshelp:link> function before calling 
    <b>NdisMRegisterInterruptEx</b>.

The miniport driver must specify entry points for the following interrupt service functions:


<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>



<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>



<mshelp:link keywords="netvista.miniportdisableinterruptex" tabindex="0"><i>
       MiniportDisableInterruptEx</i></mshelp:link>



<a href="..\ndis\nc-ndis-miniport_enable_interrupt.md">MiniportEnableInterruptEx</a>


If the NIC supports message-signaled interrupts (MSI), the miniport driver should specify entry points
    for the following MSI service functions:


<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>



<mshelp:link keywords="netvista.miniportmessageinterruptdpc" tabindex="0"><i>
       MiniportMessageInterruptDPC</i></mshelp:link>



<mshelp:link keywords="netvista.miniportdisablemessageinterrupt" tabindex="0"><i>
       MiniportDisableMessageInterrupt</i></mshelp:link>



<mshelp:link keywords="netvista.miniportenablemessageinterrupt" tabindex="0"><i>
       MiniportEnableMessageInterrupt</i></mshelp:link>


If a driver specifies entry points for MSI, it must also specify entry points for the non-MSI
    interrupt service functions. Also, if 
    <b>NdisMRegisterInterruptEx</b> returns NDIS_STATUS_SUCCESS, the driver must examine the value of the 
    <b>InterruptType</b> member of the 
    <mshelp:link keywords="netvista.ndis_miniport_interrupt_characteristics" tabindex="0"><b>
    NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</b></mshelp:link> structure to determine the type of interrupts NDIS granted.
    If NDIS cannot grant MSI support, it will grant support for line based interrupts.

When interrupts are enabled on the NIC, a driver's 
    <i>MiniportInterrupt</i>(or 
    <i>MiniportMessageInterrupt</i>) function can be called at any time after the driver calls 
    <b>NdisMRegisterInterruptEx</b>, even before 
    <b>NdisMRegisterInterruptEx</b> returns. Therefore, a driver should not call 
    <b>NdisMRegisterInterruptEx</b> until it is ready to handle an interrupt.

Drivers call the 
    <mshelp:link keywords="netvista.ndismderegisterinterruptex" tabindex="0"><b>
    NdisMDeregisterInterruptEx</b></mshelp:link> function to release resources that were previously allocated with 
    <b>NdisMRegisterInterruptEx</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Init_DeRegisterInterrupt, Init_RegisterInterrupt, Irql_Interrupt_Function, NdisMDeregisterInterruptEx |

## See Also

<a href="..\ndis\nc-ndis-miniport_message_interrupt_dpc.md">MiniportMessageInterruptDPC</a>

<a href="..\ndis\nc-ndis-miniport_isr.md">MiniportInterrupt</a>

<a href="..\ndis\nc-ndis-miniport_disable_interrupt.md">MiniportDisableInterruptEx</a>

<mshelp:link keywords="netvista.miniportenablemessageinterrupt" tabindex="0"><i>
   MiniportEnableMessageInterrupt</i></mshelp:link>

<mshelp:link keywords="netvista.miniportdisablemessageinterrupt" tabindex="0"><i>
   MiniportDisableMessageInterrupt</i></mshelp:link>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nc-ndis-miniport_enable_interrupt.md">MiniportEnableInterruptEx</a>

<mshelp:link keywords="netvista.ndis_miniport_interrupt_characteristics" tabindex="0"><b>
   NDIS_MINIPORT_INTERRUPT_CHARACTERISTICS</b></mshelp:link>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="..\ndis\nc-ndis-miniport_interrupt_dpc.md">MiniportInterruptDPC</a>

<a href="..\ndis\nf-ndis-ndismderegisterinterruptex.md">NdisMDeregisterInterruptEx</a>

<a href="..\ndis\nc-ndis-miniport_message_interrupt.md">MiniportMessageInterrupt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMRegisterInterruptEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>