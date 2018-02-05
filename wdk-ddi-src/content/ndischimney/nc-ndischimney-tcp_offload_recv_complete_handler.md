---
UID : NC:ndischimney.TCP_OFFLOAD_RECV_COMPLETE_HANDLER
title : TCP_OFFLOAD_RECV_COMPLETE_HANDLER
author : windows-driver-content
description : NDIS calls a protocol or intermediate driver's ProtocolTcpOffloadReceiveComplete function to complete a receive operation that the driver previously initiated by calling the NdisOffloadTcpReceive function.
old-location : netvista\protocoltcpoffloadreceivecomplete.htm
old-project : netvista
ms.assetid : 78201512-6b70-4b4b-9016-0f42fed41ac6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.protocoltcpoffloadreceivecomplete, ProtocolTcpOffloadReceiveComplete callback function [Network Drivers Starting with Windows Vista], ProtocolTcpOffloadReceiveComplete, TCP_OFFLOAD_RECV_COMPLETE_HANDLER, TCP_OFFLOAD_RECV_COMPLETE_HANDLER, ndischimney/ProtocolTcpOffloadReceiveComplete, tcp_chim_protocol_func_3f02ff3b-3b86-4a30-8022-2c540b5e9484.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ndischimney.h
req.include-header : Ndischimney.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PD_BUFFER_VIRTUAL_SUBNET_INFO
---


# TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback function
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

NDIS calls a protocol or intermediate driver's 
  <i>ProtocolTcpOffloadReceiveComplete</i> function to complete a receive operation that the driver previously
  initiated by calling the 
  <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpreceive.md">NdisOffloadTcpReceive</a> function.

## Syntax

```
TCP_OFFLOAD_RECV_COMPLETE_HANDLER TcpOffloadRecvCompleteHandler;

void TcpOffloadRecvCompleteHandler(
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
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function.

`NetBufferList`

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The driver
     supplied this pointer as an input parameter in a previous call to the 
     <a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpreceive.md">
     NdisOffloadTcpReceive</a> function.


## Return Value

None

## Remarks

In response to an underlying driver's or offload target's call to the 
    <a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_complete.md">
    NdisOffloadTcpReceiveComplete</a> function, NDIS calls the overlying protocol driver's or intermediate
    driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function.

To propagate the completion of the I/O operation to the overlying driver, the intermediate driver
    itself calls the 
    <b>NdisOffloadTcpReceiveComplete</b> function, passing in the following:
<ul>
<li>
A 
      <i>ProtocolBindingContext</i>, which is a handle that uniquely identifies the intermediate driver.

</li>
<li>
The PNET_BUFFER_LIST pointer that NDIS passed to the intermediate driver's 
      <i>ProtocolTcpOffloadReceiveComplete</i> function.

</li>
</ul>In response, NDIS calls the overlying driver's 
    <i>ProtocolTcpOffloadReceiveComplete</i> function, passing a 
    <i>ProtocolBindingContext</i> handle and the PNET_BUFFER_LIST pointer supplied by the intermediate driver
    to the 
    <b>NdisOffloadTcpReceiveComplete</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_receive_handler.md">MiniportTcpOffloadReceive</a>

<a href="..\ndischimney\nc-ndischimney-ndis_tcp_offload_receive_complete.md">
   NdisOffloadTcpReceiveComplete</a>

<a href="..\ndischimney\nf-ndischimney-ndisoffloadtcpreceive.md">NdisOffloadTcpReceive</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20TCP_OFFLOAD_RECV_COMPLETE_HANDLER callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>