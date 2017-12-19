---
UID: NS.NTDDNDIS._NDIS_NIC_SWITCH_VF_INFO_ARRAY
title: _NDIS_NIC_SWITCH_VF_INFO_ARRAY
author: windows-driver-content
description: The NDIS_NIC_SWITCH_VF_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.
old-location: netvista\ndis_nic_switch_vf_info_array.htm
old-project: NetVista
ms.assetid: e772eafe-e0c7-4d98-8a9e-7eb56cface37
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_NIC_SWITCH_VF_INFO_ARRAY, PNDIS_NIC_SWITCH_VF_INFO_ARRAY, NDIS_NIC_SWITCH_VF_INFO_ARRAY, *PNDIS_NIC_SWITCH_VF_INFO_ARRAY
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
req.alt-api: NDIS_NIC_SWITCH_VF_INFO_ARRAY
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

# _NDIS_NIC_SWITCH_VF_INFO_ARRAY structure



## -description
The <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.



## -syntax

````
typedef struct _NDIS_NIC_SWITCH_VF_INFO_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              Flags;
  NDIS_NIC_SWITCH_ID SwitchId;
  ULONG              FirstElementOffset;
  ULONG              NumElements;
  ULONG              ElementSize;
} NDIS_NIC_SWITCH_VF_INFO_ARRAY, *PNDIS_NIC_SWITCH_VF_INFO_ARRAY;
````


## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure. This member is formatted as an <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value: 




### -field NDIS_NIC_SWITCH_VF_INFO_ARRAY_REVISION_1

Original version for NDIS 6.30 and later.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_VF_INFO_ARRAY_REVISION_1.

</dd>
</dl>

### -field Flags

A ULONG value that contains a bitwise OR of the following flags: 




### -field NDIS_NIC_SWITCH_VF_INFO_ARRAY_ENUM_ON_SPECIFIC_SWITCH

If this flag is set, the miniport driver must only return an array of <a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a> structures for VFs that have been allocated on the network adapter switch specified by the <b>SwitchId</b> member.  For more information, see the Remarks section.

</dd>
</dl>
If the Flags member is set to zero, the miniport driver must return an array of <a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a> structures for every VF that has been allocated on every network adapter switch of the network adapter.

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default network adapter switch on the network adapter. Therefore, the miniport driver must only return an array of <a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a> structures for each VF that has been allocated on the default network adapter switch.</div>
<div> </div>

### -field SwitchId

An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default network adapter switch that is created on the network adapter. Therefore, this member must always be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

### -field FirstElementOffset

A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>

### -field NumElements

A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure. 


### -field ElementSize

A ULONG value that specifies the size, in bytes, of each element that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure.


## -remarks
NDIS returns an <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure when it handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>.  Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure is an 
    
    <a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a> structure.


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
<a href="netvista.ndis_nic_switch_vf_info">NDIS_NIC_SWITCH_VF_INFO</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_NIC_SWITCH_VF_INFO_ARRAY structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

