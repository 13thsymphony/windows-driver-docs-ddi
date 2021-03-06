---
UID: NE:netadapter._NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
title: _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
author: windows-driver-content
description: Specifies the auto-negotiation settings for the NIC driver.
ms.assetid: b7ae57e6-d3ce-409f-a737-ca303d1a58b1
ms.author: windowsdriverdev
ms.date: 02/05/2018
ms.topic: enum
ms.keywords: _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS, NET_ADAPTER_AUTO_NEGOTIATION_FLAGS, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: netadapter.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver: 1.21
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.alt-api:
req.alt-loc:
req.typenames: NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
topictype: 
-	apiref
apitype: 
-	HeaderDef
apilocation: 
-	netadapter.h
apiname: 
-	NET_ADAPTER_AUTO_NEGOTIATION_FLAGS
product: Windows
targetos: Windows
req.product: Windows 10 or later.
---

# _NET_ADAPTER_AUTO_NEGOTIATION_FLAGS enumeration

## -description

> [!WARNING]
> Some information in this topic relates to prereleased product, which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.
>
> NetAdapterCx is preview only in Windows 10, version 1803.

Specifies the auto-negotiation settings for the NIC driver.

## -enum-fields

### -field NET_ADAPTER_AUTO_NEGOTIATION_NO_FLAGS : 
No flags are set.

### -field NET_ADAPTER_LINK_STATE_XMIT_LINK_SPEED_AUTO_NEGOTIATED : 
The adapter has auto-negotiated the transmit link speed with the link partner.

### -field NET_ADAPTER_LINK_STATE_RCV_LINK_SPEED_AUTO_NEGOTIATED : 
The adapter has auto-negotiated the receive link speed with the link partner.

### -field NET_ADAPTER_LINK_STATE_DUPLEX_AUTO_NEGOTIATED : 
The adapter has auto-negotiated the duplex state with the link partner.

### -field NET_ADAPTER_LINK_STATE_PAUSE_FUNCTIONS_AUTO_NEGOTIATED : 
The adapter has auto-negotiated the pause functions with the link partner.

## -remarks

The **NET_ADAPTER_AUTO_NEGOTIATION_FLAGS** enumeration is used to specify auto-negotiation settings in the [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure.

An initialized [NET_ADAPTER_LINK_STATE](ns-netadapter-_net_adapter_link_state.md) structure is an input to [NetAdapterSetCurrentLinkState](nf-netadapter-netadaptersetcurrentlinkstate.md).



## -see-also