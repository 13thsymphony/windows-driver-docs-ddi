---
UID: NE:ntddndis._NDIS_NIC_SWITCH_TYPE
title: "_NDIS_NIC_SWITCH_TYPE"
author: windows-driver-content
description: The NDIS_NIC_SWITCH_TYPE enumeration specifies the type of the NIC switch on a network adapter.
old-location: netvista\ndis_nic_switch_type.htm
old-project: netvista
ms.assetid: F990F166-D9DA-43F5-95D3-86B9B11FACF1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE enumeration [Network Drivers Starting with Windows Vista], NdisNicSwitchTypeExternal, NdisNicSwitchTypeMax, NdisNicSwitchTypeUnspecified, PNDIS_NIC_SWITCH_TYPE, PNDIS_NIC_SWITCH_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], _NDIS_NIC_SWITCH_TYPE, netvista.ndis_nic_switch_type, ntddndis/NDIS_NIC_SWITCH_TYPE, ntddndis/NdisNicSwitchTypeExternal, ntddndis/NdisNicSwitchTypeMax, ntddndis/NdisNicSwitchTypeUnspecified, ntddndis/PNDIS_NIC_SWITCH_TYPE"
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
-	NDIS_NIC_SWITCH_TYPE
product:
- Windows
targetos: Windows
req.typenames: NDIS_NIC_SWITCH_TYPE, *PNDIS_NIC_SWITCH_TYPE
---

# _NDIS_NIC_SWITCH_TYPE Enumeration
The <b>NDIS_NIC_SWITCH_TYPE</b> enumeration specifies the type of the NIC switch on a network adapter.

## Syntax
```
typedef enum _NDIS_NIC_SWITCH_TYPE {
  NdisNicSwitchTypeUnspecified  ,
  NdisNicSwitchTypeExternal     ,
  NdisNicSwitchTypeMax
} *PNDIS_NIC_SWITCH_TYPE, NDIS_NIC_SWITCH_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>NdisNicSwitchTypeUnspecified</td>
                    <td>The NIC switch type is not specified.</td>
                </tr>
            
                <tr>
                    <td>NdisNicSwitchTypeExternal</td>
                    <td>This value specifies an external switch. The single root I/O virtualization (SR-IOV) virtual ports (VPorts) connected to this type of switch, including the default VPort, can access the external network through the physical port on the network adapter.</td>
                </tr>
            
                <tr>
                    <td>NdisNicSwitchTypeMax</td>
                    <td>The maximum value for this enumeration. This value might change in future versions of the NDIS header files and binaries.</td>
                </tr>
</table>

## Remarks

The <b>SwitchType</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh451587">NDIS_NIC_SWITCH_PARAMETERS</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh451582">NDIS_NIC_SWITCH_INFO</a> structures is an <b>NDIS_NIC_SWITCH_TYPE</b> enumeration data type. 



For more information about the NIC switch, see <a href="https://msdn.microsoft.com/548856F5-823A-4064-A6C3-28CA9FBA3860">SR-IOV Architecture</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<b></b>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451582">NDIS_NIC_SWITCH_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451587">NDIS_NIC_SWITCH_PARAMETERS</a>