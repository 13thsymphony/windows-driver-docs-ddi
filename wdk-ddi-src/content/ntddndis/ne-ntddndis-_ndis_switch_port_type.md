---
UID: NE:ntddndis._NDIS_SWITCH_PORT_TYPE
title: "_NDIS_SWITCH_PORT_TYPE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_TYPE enumeration specifies the type of a Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_type.htm
old-project: netvista
ms.assetid: 4FCE88BC-6FA1-44D0-9BC1-3065A5EEE1A0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PNDIS_SWITCH_PORT_TYPE, ntddndis/NdisSwitchPortTypeSynthetic, NdisSwitchPortTypeGeneric, ntddndis/NdisSwitchPortTypeEmulated, PNDIS_SWITCH_PORT_TYPE enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisSwitchPortTypeExternal, ntddndis/NdisSwitchPortTypeGeneric, ntddndis/NDIS_SWITCH_PORT_TYPE, NdisSwitchPortTypeExternal, NDIS_SWITCH_PORT_TYPE enumeration [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_SWITCH_PORT_TYPE, NdisSwitchPortTypeSynthetic, _NDIS_SWITCH_PORT_TYPE, netvista.ndis_switch_port_type, NDIS_SWITCH_PORT_TYPE, ntddndis/NdisSwitchPortTypeInternal, NdisSwitchPortTypeEmulated, NdisSwitchPortTypeInternal
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddndis.h
apiname:
-	NDIS_SWITCH_PORT_TYPE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_TYPE
---

# _NDIS_SWITCH_PORT_TYPE Enumeration
The <b>NDIS_SWITCH_PORT_TYPE</b> enumeration specifies the type of  a Hyper-V extensible switch port.

## Syntax
````
typedef enum _NDIS_SWITCH_PORT_TYPE { 
  NdisSwitchPortTypeGeneric    = 0,
  NdisSwitchPortTypeExternal   = 1,
  NdisSwitchPortTypeSynthetic  = 2,
  NdisSwitchPortTypeEmulated   = 3,
  NdisSwitchPortTypeInternal   = 4
} NDIS_SWITCH_PORT_TYPE, *PNDIS_SWITCH_PORT_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisSwitchPortTypeEmulated</td>
                    <td>This value specifies a port that is connected to an emulated network adapter. This adapter is exposed in a guest operating system.

<div class="alert"><b>Note</b>  An emulated network adapter is a type of VM network adapter. This adapter can be exposed in a guest operating system that is running Windows XP or a non-Windows operating system.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortTypeExternal</td>
                    <td>This value specifies a port that is connected to an external network adapter. This  adapter is exposed in the management operating system that runs in the Hyper-V parent partition. 

The external network adapter provides the connection to the  physical network interface that is available on the host. This allows processes that run in either the management or guest operating systems to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one external network adapter. The external network adapter can be bound to one or more underlying physical network adapters. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/external-network-adapters">External Network Adapters</a>.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortTypeGeneric</td>
                    <td>This value specifies a generic port type that was created with an earlier version of the extensible switch WMI management platform.</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortTypeInternal</td>
                    <td>This value specifies a port that is connected to an internal network adapter. This adapter is exposed in the management operating system that runs in the Hyper-V parent partition. 

The internal network adapter provides access to an extensible switch for processes that run in the management operating system. This allows these processes to send or receive packets over the extensible switch.

<div class="alert"><b>Note</b>  An extensible switch supports no more than one internal network adapter. For more information, see <a href="https://msdn.microsoft.com/4E4B0EC9-8E4C-47FC-B608-EC6D18367A79">Internal Network Adapters</a>.</div>
<div> </div></td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortTypeSynthetic</td>
                    <td>This value specifies a port that is connected to a synthetic network adapter. This adapter is exposed in a guest operating system that runs in a Hyper-V child partition.

<div class="alert"><b>Note</b>  A synthetic network adapter is a type of virtual machine (VM) network adapter. This adapter is exposed in a guest operating system that is running Windows Vista or a later version of Windows.</div>
<div> </div></td>
                </tr>
</table>

    ## Remarks

        The <b>PortType</b> member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a> structure is an <b>NDIS_SWITCH_PORT_TYPE</b> enumeration data type. 



For more information on the extensible switch ports, see <a href="https://msdn.microsoft.com/A9A07C71-BA64-4223-8402-254D87810167">Hyper-V Extensible Switch Ports</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETERS</a>



<b></b>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_TYPE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>