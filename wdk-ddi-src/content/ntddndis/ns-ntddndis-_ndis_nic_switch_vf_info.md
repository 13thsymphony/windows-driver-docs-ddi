---
UID: NS:ntddndis._NDIS_NIC_SWITCH_VF_INFO
title: "_NDIS_NIC_SWITCH_VF_INFO"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VF_INFO structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.
old-location: netvista\ndis_nic_switch_vf_info.htm
old-project: netvista
ms.assetid: 1af8b1cd-c594-49c7-8c25-674226295d90
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_NIC_SWITCH_VF_INFO, NDIS_NIC_SWITCH_VF_INFO, NDIS_NIC_SWITCH_VF_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_VF_INFO, PNDIS_NIC_SWITCH_VF_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_VF_INFO, netvista.ndis_nic_switch_vf_info, ntddndis/NDIS_NIC_SWITCH_VF_INFO, ntddndis/PNDIS_NIC_SWITCH_VF_INFO"
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
-	NDIS_NIC_SWITCH_VF_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_VF_INFO, *PNDIS_NIC_SWITCH_VF_INFO
---

# _NDIS_NIC_SWITCH_VF_INFO structure
The <b>NDIS_NIC_SWITCH_VF_INFO</b> structure specifies the information about a PCI Express (PCIe) Virtual Function (VF) that has been allocated on the network adapter.

## Syntax
````
typedef struct _NDIS_NIC_SWITCH_VF_INFO {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  NDIS_NIC_SWITCH_ID     SwitchId;
  NDIS_VM_NAME           VMName;
  NDIS_VM_FRIENDLYNAME   VMFriendlyName;
  NDIS_SWITCH_NIC_NAME   NicName;
  USHORT                 MacAddressLength;
  UCHAR                  PermanentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  UCHAR                  CurrentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  NDIS_SRIOV_FUNCTION_ID VFId;
  NDIS_VF_RID            RequestorId;
} NDIS_NIC_SWITCH_VF_INFO, *PNDIS_NIC_SWITCH_VF_INFO;
````

## Members


`Header`

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_NIC_SWITCH_VF_INFO_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_INFO_REVISION_1.

`Flags`

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

`SwitchId`

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the single root I/O virtualization (SR-IOV) interface only supports the default network adapter switch on the network adapter. The value of this member must be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

`VMName`

An NDIS_VM_NAME value that specifies the name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

<div class="alert"><b>Note</b>  The Hyper-V child partition is also known as a virtual machine (VM).</div>
<div> </div>

`VMFriendlyName`

An NDIS_VM_FRIENDLYNAME value that specifies the external name of the Hyper-V child partition that is attached to the VF. This member contains the user-friendly description of the partition.

`NicName`

An NDIS_SWITCH_NIC_NAME value that specifies the name of the virtual machine (VM) network adapter. This member contains the user-friendly description of the network adapter.



The VM network adapter is a virtual device that is exposed in the guest operating system that runs in a Hyper-V child partition. The VM network adapter teams with the VF network adapter to provide the hardware-based VF data path over the SR-IOV interface. 

For more information about the VF data path, see <a href="https://msdn.microsoft.com/0DC2327E-3A58-46BC-A3D6-3AFD24ABC901">SR-IOV VF Data Path</a>.

`MacAddressLength`

A USHORT value that specifies the length of the <b>PermanentMacAddress</b> and <b>CurrentMacAddress</b> members.

`PermanentMacAddress`

The permanent MAC address of the VF. This is the permanent MAC address for the VF network adapter that is exposed in the guest operating system.

`CurrentMacAddress`

The current MAC address of the VF. This is the current MAC address for the VF network adapter that is exposed in the guest operating system.

`VFId`

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

`RequestorId`

An NDIS_VF_RID that specifies the PCI Express (PCIe) Requestor ID (RID) of the VF.

## Remarks
An <b>NDIS_NIC_SWITCH_VF_INFO</b> structure contains information about a VF that was previously created through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>. When this OID request is issued, one or more <b>NDIS_NIC_SWITCH_VF_INFO</b> structures are returned within an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info_array.md">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a> structure.

For more information about the SR-IOV interface, see 	<a href="https://msdn.microsoft.com/B241F468-F568-4500-9356-E576CEBA8F3B">Overview of Single Root I/O Virtualization (SR-IOV)</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info_array.md">NDIS_NIC_SWITCH_VF_INFO_ARRAY</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<b></b>