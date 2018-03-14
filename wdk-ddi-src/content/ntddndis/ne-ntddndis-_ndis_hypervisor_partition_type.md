---
UID: NE:ntddndis._NDIS_HYPERVISOR_PARTITION_TYPE
title: "_NDIS_HYPERVISOR_PARTITION_TYPE"
author: windows-driver-content
description: The NDIS_HYPERVISOR_PARTITION_TYPE enumeration identifies the current partition type that is running on the hypervisor.
old-location: netvista\ndis_hypervisor_partition_type.htm
old-project: netvista
ms.assetid: 830460f8-4cd6-4a52-ac32-004dc4a204e3
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_HYPERVISOR_PARTITION_TYPE, NDIS_HYPERVISOR_PARTITION_TYPE, NDIS_HYPERVISOR_PARTITION_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisHypervisorPartitionMsHvChild, NdisHypervisorPartitionTypeMax, NdisHypervisorPartitionTypeMsHvParent, NdisHypervisorPartitionTypeUnknown, PNDIS_HYPERVISOR_PARTITION_TYPE, PNDIS_HYPERVISOR_PARTITION_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_HYPERVISOR_PARTITION_TYPE, netvista.ndis_hypervisor_partition_type, ntddndis/NDIS_HYPERVISOR_PARTITION_TYPE, ntddndis/NdisHypervisorPartitionMsHvChild, ntddndis/NdisHypervisorPartitionTypeMax, ntddndis/NdisHypervisorPartitionTypeMsHvParent, ntddndis/NdisHypervisorPartitionTypeUnknown, ntddndis/PNDIS_HYPERVISOR_PARTITION_TYPE, virtual_machine_queue_ref_582bebe7-e184-4460-8437-b81bcd6dbf8b.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
-	NDIS_HYPERVISOR_PARTITION_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE
---

# _NDIS_HYPERVISOR_PARTITION_TYPE Enumeration
<div class="alert"><b>Important</b>  <p class="note">Starting with Windows 10 Version 1703, NDIS_HYPERVISOR_PARTITION_TYPE is deprecated and should not be used.  Drivers are encouraged to move away from it, as it may not be available in future versions of the operating system. 

<p class="note">Drivers should instead follow a hypervisor's instructions to query hypervisor presence and capabilities. For example, Hyper-V's instructions are documented in the <a href="https://docs.microsoft.com/virtualization/hyper-v-on-windows/reference/tlfs">Top-Level Functional Specification</a>.

</div><div> </div>The <b>NDIS_HYPERVISOR_PARTITION_TYPE</b> enumeration identifies the current partition type that is running
  on the hypervisor.

## Syntax
````
typedef enum _NDIS_HYPERVISOR_PARTITION_TYPE { 
  NdisHypervisorPartitionTypeUnknown,
  NdisHypervisorPartitionTypeMsHvParent,
  NdisHypervisorPartitionMsHvChild,
  NdisHypervisorPartitionTypeMax
} NDIS_HYPERVISOR_PARTITION_TYPE, *PNDIS_HYPERVISOR_PARTITION_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisHypervisorPartitionMsHvChild</td>
                    <td>The child partition is running on
     the Microsoft hypervisor.</td>
                </tr>
            
                <tr>
                    <td>NdisHypervisorPartitionTypeMax</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.</td>
                </tr>
            
                <tr>
                    <td>NdisHypervisorPartitionTypeMsHvParent</td>
                    <td>The parent partition (also known as the root partition) is running
     on the Microsoft hypervisor.</td>
                </tr>
            
                <tr>
                    <td>NdisHypervisorPartitionTypeUnknown</td>
                    <td>The partition type that is running on the hypervisor is not known.

<div class="alert"><b>Note</b>  This enumeration value is used to identify a partition type for a third-party hypervisor.</div>
<div> </div></td>
                </tr>
</table>

## Remarks

For more information about Hyper-V parent and child partitions, see <a href="https://msdn.microsoft.com/467996B2-9319-47F9-BAEB-5AC1F20B6E01">Virtualized Networking Concepts and Terms</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.20 and later. Supported in NDIS 6.20 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_hypervisor_info.md">NDIS_HYPERVISOR_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_HYPERVISOR_PARTITION_TYPE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>