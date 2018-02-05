---
UID : NF:vmbuskernelmodeclientlibapi.VmbChannelSetTransactionQuota
title : VmbChannelSetTransactionQuota function
author : windows-driver-content
description : The VmbChannelSetTransactionQuota function sets the incoming packet quota.
old-location : netvista\vmbchannelsettransactionquota.htm
old-project : netvista
ms.assetid : C88F03BE-96D3-46A7-8269-1ECBFA539111
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : vmbuskernelmodeclientlibapi/VmbChannelSetTransactionQuota, netvista.vmbchannelsettransactionquota, VmbChannelSetTransactionQuota function [Network Drivers Starting with Windows Vista], VmbChannelSetTransactionQuota
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
req.typenames : "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product : Windows 10 or later.
---


# VmbChannelSetTransactionQuota function
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetTransactionQuota</b> function sets the incoming packet quota.

## Syntax

````
VOID VmbChannelSetTransactionQuota(
  _In_ VMBCHANNEL Channel,
  _In_ UINT32     Quota
);
````

## Parameters

`Channel`

A handle for a channel.

`Quota`

The maximum outstanding packet quota. This value must be greater than 0.


## Return Value

This function does not return a value.

## Remarks

The incoming packet quota can be set to be lower than the current
outstanding packet count. In that case, no new packets are removed from
the queue until sufficient packets have been completed.


 If the queue is currently blocked due to quota, this operation does not restart it. The queue only restarts once a packet is completed.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.13 |
| **Minimum UMDF version** | 2.0 |
| **Header** | vmbuskernelmodeclientlibapi.h (include VmbusKernelModeClientLibApi.h) |
| **Library** | Vmbkmcl.lib |