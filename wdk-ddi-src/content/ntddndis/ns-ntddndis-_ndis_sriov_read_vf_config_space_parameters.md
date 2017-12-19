---
UID: NS.NTDDNDIS._NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS
title: _NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS
author: windows-driver-content
description: The NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS structure specifies the parameters for a read operation on the PCI Express (PCIe) configuration space of a network adapter's Virtual Function (VF).
old-location: netvista\ndis_sriov_read_vf_config_space_parameters.htm
old-project: NetVista
ms.assetid: aa127aa2-8002-4e96-8822-ed66291edf6e
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS, *PNDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS, NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS, PNDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS
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
req.alt-api: NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS
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

# _NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS structure



## -description
The <b>NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS</b> structure specifies the parameters for a read operation on the PCI Express (PCIe) configuration space  of a network adapter's Virtual Function (VF).



## -syntax

````
typedef struct _NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  NDIS_SRIOV_FUNCTION_ID VFId;
  ULONG                  Offset;
  ULONG                  Length;
  ULONG                  BufferOffset;
} NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS, *PNDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS_REVISION_1.

</dd>
</dl>

### -field VFId

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.

<div class="alert"><b>Note</b>  The VF with the specified NDIS_SRIOV_FUNCTION_ID value must have resources that were previously allocated through an OID set request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div>
<div> </div>

### -field Offset

A ULONG value that specifies the offset within the PCI configuration space of the VF in which data will be read.


### -field Length

A ULONG value that specifies the length, in units of bytes, of the read operation.


### -field BufferOffset

A ULONG value that specifies the offset, in units of bytes, from the beginning of this structure to a buffer that contains the data that is read from the PCI configuration space of the VF.


## -remarks
 The <b>NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS</b> structure is used in OID method requests of  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451879">OID_SRIOV_READ_VF_CONFIG_SPACE</a>.


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
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451879">OID_SRIOV_READ_VF_CONFIG_SPACE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_SRIOV_READ_VF_CONFIG_SPACE_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

