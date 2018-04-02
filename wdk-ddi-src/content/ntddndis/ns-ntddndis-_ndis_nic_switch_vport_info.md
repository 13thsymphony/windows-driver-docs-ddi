---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VPORT_INFO
title: "_NDIS_NIC_SWITCH_VPORT_INFO"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_INFO structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter.
old-location: netvista\ndis_nic_switch_vport_info.htm
old-project: netvista
ms.assetid: 5effb179-18e8-4306-84c5-724cb5483449
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_INFO, NDIS_NIC_SWITCH_VPORT_INFO, NDIS_NIC_SWITCH_VPORT_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VPORT_INFO, PNDIS_NIC_SWITCH_VPORT_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_INFO, netvista.ndis_nic_switch_vport_info, ntddndis/NDIS_NIC_SWITCH_VPORT_INFO, ntddndis/PNDIS_NIC_SWITCH_VPORT_INFO"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddndis.h
api_name:
-	NDIS_NIC_SWITCH_VPORT_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_INFO, *PNDIS_NIC_SWITCH_VPORT_INFO
---

# _NDIS_NIC_SWITCH_VPORT_INFO structure
The <b>NDIS_NIC_SWITCH_VPORT_INFO</b> structure specifies the configuration for a virtual port (VPort) on a network adapter switch of the network adapter.

## Syntax
```
typedef struct _NDIS_NIC_SWITCH_VPORT_INFO {
  NDIS_OBJECT_HEADER                         Header;
  NDIS_NIC_SWITCH_VPORT_ID                   VPortId;
  ULONG                                      Flags;
  NDIS_NIC_SWITCH_ID                         SwitchId;
  NDIS_VPORT_NAME                            VPortName;
  NDIS_SRIOV_FUNCTION_ID                     AttachedFunctionId;
  ULONG                                      NumQueuePairs;
  NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION InterruptModeration;
  NDIS_NIC_SWITCH_VPORT_STATE                VPortState;
  GROUP_AFFINITY                             ProcessorAffinity;
  ULONG                                      LookaheadSize;
  ULONG                                      NumFilters;
} NDIS_NIC_SWITCH_VPORT_INFO, *PNDIS_NIC_SWITCH_VPORT_INFO;
```

## Members


`Header`

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VPORT_INFO</b> structure. This member is formatted as an <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VPORT_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VPORT_INFO_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VPORT_INFO_REVISION_1.

`VPortId`

An NDIS_NIC_SWITCH_VPORT_ID value  that uniquely identifies the virtual port (VPort)  on the network adapter. 

A value of NDIS_DEFAULT_VPORT_ID specifies the default VPort on the switch. The default

VPort is always attached to the PCI Express (PCIe) Physical Function (PF) of the network adapter.

<div class="alert"><b>Note</b>  A nondefault VPort with the specified <b>VPortId</b> value must have previously been created through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.</div>
<div> </div>

`Flags`

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

`SwitchId`

An NDIS_NIC_SWITCH_ID value that uniquely identifies  a network adapter switch that was created on the network adapter. The VPort identified through the <b>VPortId</b> member is created on the switch specified by the <b>SwitchId</b> member.

The switch identifier is an integer between zero and the number of switches that the network adapter supports. A value of NDIS_DEFAULT_SWITCH_ID indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

`VPortName`

An NDIS_VPORT_NAME value that  specifies the name of the VPort that was created on the network adapter switch. This member contains the user-friendly description of the VPort.

`AttachedFunctionId`

An NDIS_SRIOV_FUNCTION_ID value that specifies the identifier of a VF or the PF to which the  VPort is attached. 

<div class="alert"><b>Note</b>  If this value is NDIS_PF_FUNCTION_ID, the VPort is attached to the PF.</div>
<div> </div>

`NumQueuePairs`

A ULONG value that specifies the number of queue pairs configured for this VPort.

A queue pair consists of a transmit queue and receive queue. Queue pairs associated with the default VPort are configured at the time of switch creation through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451815">OID_NIC_SWITCH_CREATE_SWITCH</a>.
One or more queue pairs are configured on a nondefault VPort through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.

`InterruptModeration`

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451596">NDIS_NIC_SWITCH_VPORT_INTERRUPT_MODERATION</a> value that specifies the interrupt moderation setting of the VPort.

`VPortState`

An <a href="https://msdn.microsoft.com/library/windows/hardware/hh451598">NDIS_NIC_SWITCH_VPORT_STATE</a> value that specifies the state of the VPort.

`ProcessorAffinity`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff546539">GROUP_AFFINITY</a> value that specifies the group number and a bitmap of the CPUs that this VPort can be associated with. 

This member is valid only for the VPorts attached to the PF. This field is not valid for nondefault VPorts that are attached to a VF.

`LookaheadSize`

This member is reserved for future use. This member must be set to zero.

`NumFilters`

A ULONG value that specifies the number of receive filters that have been configured on the network adapter.

<div class="alert"><b>Note</b>  Starting with NDIS 6.30, the miniport driver must maintain a counter for the current number of receive filters that are set on the network adapter. The driver must increment the counter each time a receive filter is set through an OID set request of <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-receive-filter-set-filter">OID_RECEIVE_FILTER_SET_FILTER</a>.  The driver must also decrement the counter each time a receive filter is  cleared through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/ff569785">OID_RECEIVE_FILTER_CLEAR_FILTER</a>.</div>
<div> </div>

## Remarks
An <b>NDIS_NIC_SWITCH_VPORT_INFO</b> structure contains information about one of the following:<ul>
<li>
A nondefault VPort that was previously created through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>.

</li>
<li>
The default VPort that is attached to the PF. The default VPort always exists and cannot be deleted.

</li>
</ul>


One or more <b>NDIS_NIC_SWITCH_VPORT_INFO</b> structures are returned through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451595">NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</a> structure.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451595">NDIS_NIC_SWITCH_VPORT_INFO_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451816">OID_NIC_SWITCH_CREATE_VPORT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>