---
UID: NS.ntddndis._NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
title: NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
author: windows-driver-content
description: The NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure specifies the parameters for a read operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF).
old-location: netvista\ndis_sriov_read_vf_config_block_parameters.htm
old-project: netvista
ms.assetid: fafad6f2-8092-4067-afad-208877309010
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, *PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
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
req.alt-api: NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS
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
req.iface: 
---

# NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure



## -description
<p>The <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure specifies the parameters for a read operation on the configuration block of a network adapter's PCI Express (PCIe) Virtual Function (VF). These parameters are used for the backchannel communication between the miniport drivers for a VF and the PCIe Physical Function (PF).</p>


## -syntax

````
typedef struct _NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  ULONG                  BlockId;
  ULONG                  Length;
  ULONG                  BufferOffset;
} NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS, *PNDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The type, revision, and size of the <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure.</p>
<p>The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: </p>
<p></p>
<dl>

### -field NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1

<dd>
<p>Original version for NDIS 6.30 and later.</p>
<p>Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS_REVISION_1.</p>
</dd>
</dl>
</dd>

### -field VFId

<dd>
<p>An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.</p>
<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>
</dd>

### -field BlockId

<dd>
<p>A ULONG value that specifies the identifier of the VF configuration block to be read. This identifier is proprietary to the independent hardware vendor (IHV) and is used only by the miniport drivers for the PF and VF on the network adapter.
</p>
<p>For more information, see the Remarks section.</p>
</dd>

### -field Length

<dd>
<p>A ULONG value that specifies the length, in units of bytes, of the read operation.</p>
</dd>

### -field BufferOffset

<dd>
<p>A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data that is read from the specified VF configuration block.</p>
</dd>
</dl>

## -remarks
<p>The <b>NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS</b> structure is used in OID method requests of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451874">OID_SRIOV_READ_VF_CONFIG_BLOCK</a>.</p>

<p>A VF configuration block is used for backchannel communication between the drivers of the PCIe PF and a VF on a device that supports the SR-IOV interface. Data from a VF configuration block can be exchanged between the following drivers:</p>

<p>The VF miniport driver, which runs in the guest operating system. This operating system runs within a Hyper-V child partition.

</p>

<p>The PF miniport driver, which runs in the management operating system.

This operating system runs within the Hyper-V parent partition.</p>

<p>For more information about backchannel communication within the single root I/O virtualization (SR-IOV) interface, see <a href="netvista.sr_iov_pf_vf_backchannel_communication">SR-IOV PF/VF Backchannel Communication</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.30 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451874">OID_SRIOV_READ_VF_CONFIG_BLOCK</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SRIOV_READ_VF_CONFIG_BLOCK_PARAMETERS structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
