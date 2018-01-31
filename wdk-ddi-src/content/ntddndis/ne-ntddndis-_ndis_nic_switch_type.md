---
UID : NE:ntddndis._NDIS_NIC_SWITCH_TYPE
title : "_NDIS_NIC_SWITCH_TYPE"
author : windows-driver-content
description : The NDIS_NIC_SWITCH_TYPE enumeration specifies the type of the NIC switch on a network adapter.
old-location : netvista\ndis_nic_switch_type.htm
old-project : netvista
ms.assetid : F990F166-D9DA-43F5-95D3-86B9B11FACF1
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddndis/NdisNicSwitchTypeMax, PNDIS_NIC_SWITCH_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], NdisNicSwitchTypeUnspecified, *PNDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE enumeration [Network Drivers Starting with Windows Vista], ntddndis/NDIS_NIC_SWITCH_TYPE, ntddndis/NdisNicSwitchTypeUnspecified, NDIS_NIC_SWITCH_TYPE, _NDIS_NIC_SWITCH_TYPE, NdisNicSwitchTypeExternal, PNDIS_NIC_SWITCH_TYPE, ntddndis/PNDIS_NIC_SWITCH_TYPE, NdisNicSwitchTypeMax, netvista.ndis_nic_switch_type, ntddndis/NdisNicSwitchTypeExternal
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
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
req.typenames : NDIS_NIC_SWITCH_TYPE, *PNDIS_NIC_SWITCH_TYPE
---

# _NDIS_NIC_SWITCH_TYPE Enumeration
The <b>NDIS_NIC_SWITCH_TYPE</b> enumeration specifies the type of the NIC switch on a network adapter.

## Syntax
````
typedef enum _NDIS_NIC_SWITCH_TYPE { 
  NdisNicSwitchTypeUnspecified  = 0,
  NdisNicSwitchTypeExternal     = 1,
  NdisNicSwitchTypeMax          = 2
} NDIS_NIC_SWITCH_TYPE, *PNDIS_NIC_SWITCH_TYPE;
````

## Constants

<table>

<tr>
<td>NdisNicSwitchTypeExternal</td>
<td>This value specifies an external switch. The single root I/O virtualization (SR-IOV) virtual ports (VPorts) connected to this type of switch, including the default VPort, can access the external network through the physical port on the network adapter.</td>
</tr>

<tr>
<td>NdisNicSwitchTypeMax</td>
<td>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.</td>
</tr>

<tr>
<td>NdisNicSwitchTypeUnspecified</td>
<td>The NIC switch type is not specified.</td>
</tr>
</table>

## Remarks

The <b>SwitchType</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_parameters.md">NDIS_NIC_SWITCH_PARAMETERS</a> and <a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info.md">NDIS_NIC_SWITCH_INFO</a> structures is an <b>NDIS_NIC_SWITCH_TYPE</b> enumeration data type. 



For more information about the NIC switch, see <a href="https://msdn.microsoft.com/548856F5-823A-4064-A6C3-28CA9FBA3860">SR-IOV Architecture</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_info.md">NDIS_NIC_SWITCH_INFO</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_nic_switch_parameters.md">NDIS_NIC_SWITCH_PARAMETERS</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_NIC_SWITCH_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>