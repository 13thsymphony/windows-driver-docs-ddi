---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelPacketComplete
title : VmbChannelPacketComplete function
author : windows-driver-content
description : The VmbChannelPacketComplete function cleans up any outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a completion packet.
old-location : netvista\vmbchannelpacketcomplete.htm
old-project : netvista
ms.assetid : 1DC215DF-1F53-4910-84D5-17E13BE6202A
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : VmbChannelPacketComplete, VmbChannelPacketComplete function [Network Drivers Starting with Windows Vista], vmbuskernelmodeclientlibapi/VmbChannelPacketComplete, netvista.vmbchannelpacketcomplete
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : vmbuskernelmodeclientlibapi.h
req.include-header : VmbusKernelModeClientLibApi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 1.13
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Vmbkmcl.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product : Windows 10 or later.
---


# VmbChannelPacketComplete function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelPacketComplete</b>  function cleans up any
outstanding memory mappings, releases any buffers in use, and, if the opposite endpoint requested a completion packet, sends a
completion packet.

## Syntax

````
VOID VmbChannelPacketComplete(
  _In_ VMBPACKETCOMPLETION             PacketCompletionContext,
  _In_ reads_bytes_opt_(BufSize) PVOID PacketCompletionBuffer,
  _In_ UINT32                          BufSize
);
````

## Parameters

`PacketCompletionContext`

A  handle that identifies the incoming packet and is used to refer to the packet
once processing is finished.

`PacketCompletionBuffer`

A buffer of completion data to be sent back to the originating endpoint.  Although this usually contains just a status value, the contents are up to the client driver.

`BufSize`

The size, in bytes, of the completion buffer.


## Return Value

This function does not return a value.

## Remarks

This function is called when the client driver is finished
processing a packet.  This function may be called directly from the packet parsing function
or it may be called later.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |