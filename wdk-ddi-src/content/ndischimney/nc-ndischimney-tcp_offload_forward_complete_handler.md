---
UID: NC:ndischimney.TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
title: TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER
author: windows-driver-content
description: NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadForwardComplete function to complete a forward operation that the driver previously initiated by calling the NdisOffloadTcpForward function.
old-location: netvista\protocoltcpoffloadforwardcomplete.htm
old-project: netvista
ms.assetid: 02a11841-d98a-4c74-8922-458826e2911e
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: ProtocolTcpOffloadForwardComplete, ProtocolTcpOffloadForwardComplete callback function [Network Drivers Starting with Windows Vista], TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadForwardComplete, netvista.protocoltcpoffloadforwardcomplete, tcp_chim_protocol_func_18981e3f-fec9-483d-b60e-54017ebd57d1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Ndischimney.h
api_name:
-	ProtocolTcpOffloadForwardComplete
product:
- Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadForwardComplete</i> function to complete a forward operation that the driver previously
  initiated by calling the 
  <a href="https://msdn.microsoft.com/f8abff30-b641-4581-8532-8292993ca9f6">
  NdisOffloadTcpForward</a> function.

## Syntax

```
TCP_OFFLOAD_FORWARD_COMPLETE_HANDLER TcpOffloadForwardCompleteHandler;

void TcpOffloadForwardCompleteHandler(
  IN NDIS_HANDLE ProtocolBindingContext,
  IN PNET_BUFFER_LIST NetBufferList
)
{...}
```

## Parameters

`ProtocolBindingContext`

A handle to a context area allocated by the protocol driver. The driver maintains the per binding
     context information in this context area. The driver supplied this handle to NDIS when the driver called
     the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function.

`NetBufferList`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <b>NdisOffloadTcpForward</b> function.


## Return Value

None

## Remarks

In response to an underlying driver's or offload target's call to the 
    <b>NdisOffloadTcpForwardComplete</b> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadForwardComplete</i> function.

To propagate the completion of the forward operation to the overlying driver or host stack, the
    intermediate driver calls the 
    <b>NdisOffloadTcpForwardComplete</b> function, passing in the following:

<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadForwardComplete</i> function.

</li>
</ul>
In response, NDIS calls the overlying driver's or host stack's 
    <i>ProtocolTcpOffloadForwardComplete</i> function, passing in a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpForwardComplete</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">MiniportTcpOffloadForward</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563702">NdisOffloadTcpForward</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/080949ab-8a27-4d13-992e-597210d4882c">
   NdisTcpOffloadForwardComplete</a>