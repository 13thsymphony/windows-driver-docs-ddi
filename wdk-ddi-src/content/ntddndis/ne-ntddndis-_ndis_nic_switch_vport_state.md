---
UID: NE:ntddndis._NDIS_NIC_SWITCH_VPORT_STATE
title: "_NDIS_NIC_SWITCH_VPORT_STATE"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VPORT_STATE enumeration specifies the state of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch of a network adapter.
old-location: netvista\ndis_nic_switch_vport_state.htm
old-project: netvista
ms.assetid: 25999016-95a8-4d78-a4a3-111fc4e910ad
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VPORT_STATE, NDIS_NIC_SWITCH_VPORT_STATE, NDIS_NIC_SWITCH_VPORT_STATE enumeration [Network Drivers Starting with Windows Vista], NdisNicSwitchVPortStateActivated, NdisNicSwitchVPortStateDeactivated, NdisNicSwitchVPortStateMaximum, NdisNicSwitchVPortStateUndefined, PNDIS_NIC_SWITCH_VPORT_STATE, PNDIS_NIC_SWITCH_VPORT_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VPORT_STATE, netvista.ndis_nic_switch_vport_state, ntddndis/NDIS_NIC_SWITCH_VPORT_STATE, ntddndis/NdisNicSwitchVPortStateActivated, ntddndis/NdisNicSwitchVPortStateDeactivated, ntddndis/NdisNicSwitchVPortStateMaximum, ntddndis/NdisNicSwitchVPortStateUndefined, ntddndis/PNDIS_NIC_SWITCH_VPORT_STATE"
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
-	NDIS_NIC_SWITCH_VPORT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VPORT_STATE, *PNDIS_NIC_SWITCH_VPORT_STATE
---

# _NDIS_NIC_SWITCH_VPORT_STATE Enumeration
The <b>NDIS_NIC_SWITCH_VPORT_STATE</b> enumeration specifies the state of a single root I/O virtualization (SR-IOV) virtual port (VPort) on the NIC switch of a network adapter.

## Syntax
````
typedef enum _NDIS_NIC_SWITCH_VPORT_STATE { 
  NdisNicSwitchVPortStateUndefined    = 0,
  NdisNicSwitchVPortStateActivated    = 1,
  NdisNicSwitchVPortStateDeactivated  = 2,
  NdisNicSwitchVPortStateMaximum      = 3
} NDIS_NIC_SWITCH_VPORT_STATE, *PNDIS_NIC_SWITCH_VPORT_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisNicSwitchVPortStateUndefined</td>
                    <td>The VPort state is not defined.</td>
                </tr>
            
                <tr>
                    <td>NdisNicSwitchVPortStateActivated</td>
                    <td>The VPort is allocated and in an activated state.

<div class="alert"><b>Note</b>  The default VPort attached to the PCI Express (PCIe) Physical Function (PF) and nondefault VPorts attached to PCIe Virtual Functions (VFs) are created in an activated state. Once created, these VPorts cannot be deactivated.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>NdisNicSwitchVPortStateDeactivated</td>
                    <td>The VPort is allocated and in a deactivated state.

<div class="alert"><b>Note</b>  Nondefault VPorts attached to the PF are created in a deactivated state. These VPorts can be activated by using OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>. However, once activated, these VPorts cannot be deactivated.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>NdisNicSwitchVPortStateMaximum</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.</td>
                </tr>
</table>

## Remarks

The <b>VPortState</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_parameters.md">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a> and <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_info.md">NDIS_NIC_SWITCH_VPORT_INFO</a> structures is an <b>NDIS_NIC_SWITCH_VPORT_STATE</b> enumeration data type.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_parameters.md">NDIS_NIC_SWITCH_VPORT_PARAMETERS</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vport_info.md">NDIS_NIC_SWITCH_VPORT_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451825">OID_NIC_SWITCH_VPORT_PARAMETERS</a>



<b></b>