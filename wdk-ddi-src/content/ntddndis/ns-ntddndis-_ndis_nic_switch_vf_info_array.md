---
UID : NS:ntddndis._NDIS_NIC_SWITCH_VF_INFO_ARRAY
title : _NDIS_NIC_SWITCH_VF_INFO_ARRAY
author : windows-driver-content
description : The NDIS_NIC_SWITCH_VF_INFO_ARRAY structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.
old-location : netvista\ndis_nic_switch_vf_info_array.htm
old-project : netvista
ms.assetid : e772eafe-e0c7-4d98-8a9e-7eb56cface37
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _NDIS_NIC_SWITCH_VF_INFO_ARRAY, NDIS_NIC_SWITCH_VF_INFO_ARRAY, *PNDIS_NIC_SWITCH_VF_INFO_ARRAY
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NDIS_NIC_SWITCH_VF_INFO_ARRAY
req.alt-loc : Ntddndis.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : NDIS_NIC_SWITCH_VF_INFO_ARRAY, *PNDIS_NIC_SWITCH_VF_INFO_ARRAY
---

# _NDIS_NIC_SWITCH_VF_INFO_ARRAY structure
The <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure specifies an array. Each element in the array specifies the attributes of a PCI Express (PCIe) virtual functions (VF) that have been enabled and allocated on a network adapter.

## Syntax
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

## Members

        
            `ElementSize`

            A ULONG value that specifies the size, in bytes, of each element that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure.
        
            `FirstElementOffset`

            A ULONG value that specifies the offset, in bytes, to the first element in an array of elements that follow this structure. The offset is measured from the start of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure up to the beginning of the first element. Each element in the array is an <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info.md">NDIS_NIC_SWITCH_VF_INFO</a> structure.



<div class="alert"><b>Note</b>  If <b>NumElements</b> is set to zero, this member is ignored.  </div>
<div> </div>
        
            `Flags`

            A ULONG value that contains a bitwise OR of the following flags:
        
            `Header`

            The type, revision, and size of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

NDIS sets the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure, NDIS sets the <b>Revision</b> member of <b>Header</b> to the following value:
        
            `NumElements`

            A ULONG value that specifies the number of elements that follow the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure.
        
            `SwitchId`

            An NDIS_NIC_SWITCH_ID value that specifies a switch identifier. The switch identifier is an integer between zero and the number of switches that the network adapter supports. An NDIS_DEFAULT_SWITCH_ID value indicates the default network adapter switch.



<div class="alert"><b>Note</b>  Starting with Windows Server 2012, the SR-IOV interface only supports the default network adapter switch that is created on the network adapter. Therefore, this member must always be set to NDIS_DEFAULT_SWITCH_ID. </div>
<div> </div>

    ## Remarks
        NDIS returns an <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure when it handles an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>.  Each
    element in the array that follows the <b>NDIS_NIC_SWITCH_VF_INFO_ARRAY</b> structure is an 
    
    <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info.md">NDIS_NIC_SWITCH_VF_INFO</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <dl>
<dt><b></b></dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_vf_info.md">NDIS_NIC_SWITCH_VF_INFO</a>
</dt>
<dt>
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451820">OID_NIC_SWITCH_ENUM_VFS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_VF_INFO_ARRAY structure%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>