---
UID: NS:ntddndis._NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS
title: "_NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS"
author: windows-driver-content
description: The NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure specifies the parameters for a write operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF).
old-location: netvista\ndis_sriov_write_vf_config_block_parameters.htm
old-project: netvista
ms.assetid: bcf20a21-46a8-41e6-ae6e-bef8d6735c82
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure [Network Drivers Starting with Windows Vista], *PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, ntddndis/PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, netvista.ndis_sriov_write_vf_config_block_parameters, NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS"
---

# _NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure
The <b>NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS</b> structure specifies the parameters for a write operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF). These parameters are used for the backchannel communication between the VF and the PCIe Physical Function (PF) miniport drivers.

## Syntax
````
typedef struct _NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  ULONG                  BlockId;
  ULONG                  Length;
  ULONG                  BufferOffset;
} NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS, *PNDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS;
````

## Members


`BlockId`

A ULONG value that specifies the identifier of the VF configuration block to be written to. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the miniport drivers for the PF and VF on the network adapter.


For more information, see the Remarks section.

`BufferOffset`

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data to be written to the specified VF configuration block.

`Header`

The type, revision, and size of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 





#### NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1.

`Length`

A ULONG value that specifies the length, in units of bytes, of the write operation.

`VFId`

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an object identifier (OID) method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

## Remarks
The <b>NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS</b> structure is used in an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451918">OID_SRIOV_WRITE_VF_CONFIG_BLOCK</a>. 

A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:

<ul>
<li>
The VF miniport driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.



</li>
<li>
The PF miniport driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.

</li>
</ul>
<div class="alert"><b>Note</b>  The  usage of the VF configuration block and the format of its configuration data are defined by the  independent hardware vendor (IHV) of the device. The configuration data is used only by the PF and VF miniport drivers.</div>
<div> </div>
For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="https://msdn.microsoft.com/66D40452-1286-449E-BD6B-AFAD466E03A1">SR-IOV PF/VF Backchannel Communication</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451918">OID_SRIOV_WRITE_VF_CONFIG_BLOCK</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_WRITE_VF_CONFIG_BLOCK_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>