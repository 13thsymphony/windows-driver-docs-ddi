---
UID : NS:ntddndis._NDIS_NIC_SWITCH_FREE_VF_PARAMETERS
title : "_NDIS_NIC_SWITCH_FREE_VF_PARAMETERS"
author : windows-driver-content
description : The NDIS_NIC_SWITCH_FREE_VF_PARAMETERS specifies a PCI Express (PCIe) Virtual Function (VF) whose resources will be freed.
old-location : netvista\ndis_nic_switch_free_vf_parameters.htm
old-project : netvista
ms.assetid : 61f3839a-f428-4585-a046-edce85d829dd
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, netvista.ndis_nic_switch_free_vf_parameters, PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS, ntddndis/NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, *PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS, _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, *PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS
---

# _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure
The <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> specifies a PCI Express (PCIe) Virtual Function (VF) whose resources will be freed.

## Syntax
````
typedef struct _NDIS_NIC_SWITCH_FREE_VF_PARAMETERS {
  NDIS_OBJECT_HEADER     Header;
  ULONG                  Flags;
  NDIS_SRIOV_FUNCTION_ID VFId;
} NDIS_NIC_SWITCH_FREE_VF_PARAMETERS, *PNDIS_NIC_SWITCH_FREE_VF_PARAMETERS;
````

## Members


`Flags`

A ULONG value that contains a bitwise OR of flags. This member is reserved for NDIS.

`Header`

The type, revision, and size of the <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure. This member is formatted as an <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_DEFAULT. To specify the version of the <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to the following value: 




#### NDIS_NIC_SWITCH_FREE_VF_PARAMETERS_REVISION_1

Original version for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_NIC_SWITCH_FREE_VF_PARAMETERS_REVISION_1.

`VFId`

An NDIS_SRIOV_FUNCTION_ID value that specifies the unique identifier of the VF on the network adapter.
<div class="alert"><b>Note</b>  Resources for the VF with the specified NDIS_SRIOV_FUNCTION_ID value must have previously been allocated through an OID method request of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>.

</div><div> </div>

## Remarks
The <b>NDIS_NIC_SWITCH_FREE_VF_PARAMETERS</b> structure is used in OID set requests of <a href="https://msdn.microsoft.com/library/windows/hardware/hh451822">OID_NIC_SWITCH_FREE_VF</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451814">OID_NIC_SWITCH_ALLOCATE_VF</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451822">OID_NIC_SWITCH_FREE_VF</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_FREE_VF_PARAMETERS structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>