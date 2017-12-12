---
UID: NE.ntddndis._NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
title: _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.
old-location: netvista\ndis_nic_switch_vport_interrupt_moderation.htm
old-project: netvista
ms.assetid: 86ec2e8f-1a89-4c0a-b761-d9bf0d3dc35a
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION
req.alt-loc: Ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration



## -description
The <b>NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION</b> enumeration specifies the interrupt moderation setting of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch.



## -syntax

````
typedef enum _NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION { 
  NdisNicSwitchVPortIntModUndefined  = 0,
  NdisNicSwitchVPortIntModAdaptive   = 1,
  NdisNicSwitchVPortIntModOff        = 2,
  NdisNicSwitchVPortIntModLow        = 100,
  NdisNicSwitchVPortIntModMedium     = 200,
  NdisNicSwitchVPortIntModHigh       = 300
} NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION, *PNDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION;
````


## -enum-fields

### -field NdisNicSwitchVPortIntModUndefined

Interrupt moderation for the VPort is not defined.


### -field NdisNicSwitchVPortIntModAdaptive

Interrupt moderation for the VPort is adaptive. This state enables the network adapter to adjust the interrupt moderation rate for the VPort based on the pattern of network traffic.


### -field NdisNicSwitchVPortIntModOff

Interrupt moderation for the VPort is disabled.


### -field NdisNicSwitchVPortIntModLow

Interrupt moderation for the VPort is low.


### -field NdisNicSwitchVPortIntModMedium

Interrupt moderation for the VPort is medium.


### -field NdisNicSwitchVPortIntModHigh

Interrupt moderation for the VPort is high.


## -remarks
The determination of low, medium, and high interrupt moderation levels is determined by the miniport driver based on a hardware algorithm that is based on the network adapter.

The <b>InterruptModeration</b> member of the <a href="netvista.ndis_nic_switch_vport_parameters">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> and <a href="netvista.ndis_nic_switch_vport_info">NDIS_NIC_SWITCH_VPORT_INFO</a> structures is an NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration data type. 


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt><b></b></dt>
<dt>
<a href="netvista.ndis_nic_switch_vport_info">NDIS_NIC_SWITCH_VPORT_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_nic_switch_vport_parameters">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

