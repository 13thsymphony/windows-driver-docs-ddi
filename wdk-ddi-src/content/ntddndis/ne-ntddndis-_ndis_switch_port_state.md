---
UID: NE:ntddndis._NDIS_SWITCH_PORT_STATE
title: "_NDIS_SWITCH_PORT_STATE"
author: windows-driver-content
description: The NDIS_SWITCH_PORT_STATE enumeration specifies the current state of the Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_state.htm
old-project: netvista
ms.assetid: BEF37F32-036D-4381-93B3-C159ABCFC3F9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NdisSwitchPortStateCreated, ntddndis/NdisSwitchPortStateDeleted, NdisSwitchPortStateUnknown, netvista.ndis_switch_port_state, NdisSwitchPortStateDeleted, NDIS_SWITCH_PORT_STATE, ntddndis/NdisSwitchPortStateTeardown, NdisSwitchPortStateTeardown, _NDIS_SWITCH_PORT_STATE, NDIS_SWITCH_PORT_STATE enumeration [Network Drivers Starting with Windows Vista], NdisSwitchPortStateCreated, ntddndis/NdisSwitchPortStateUnknown, ntddndis/NDIS_SWITCH_PORT_STATE
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
-	NDIS_SWITCH_PORT_STATE
product: Windows
targetos: Windows
req.typenames: NDIS_SWITCH_PORT_STATE
---

# _NDIS_SWITCH_PORT_STATE Enumeration
The <b>NDIS_SWITCH_PORT_STATE</b> enumeration specifies the current state of the Hyper-V extensible switch port.

## Syntax
````
typedef enum _NDIS_SWITCH_PORT_STATE { 
  NdisSwitchPortStateUnknown   = 0,
  NdisSwitchPortStateCreated   = 1,
  NdisSwitchPortStateTeardown  = 2,
  NdisSwitchPortStateDeleted   = 3
} NDIS_SWITCH_PORT_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>NdisSwitchPortStateCreated</td>
                    <td>This value specifies that the port is in the created state.</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortStateDeleted</td>
                    <td>This value specifies that the port has been deleted.</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortStateTeardown</td>
                    <td>This value specifies that the port is being torn down.</td>
                </tr>
            
                <tr>
                    <td>NdisSwitchPortStateUnknown</td>
                    <td>This value specifies an undefined port state. This value is unused.</td>
                </tr>
</table>

    ## Remarks

        The <b>PortState</b>  member of the <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETER</a> structure is an <b>NDIS_SWITCH_PORT_STATE</b> enumeration data type. 


For more information about extensible switch port states, see <a href="https://msdn.microsoft.com/FD6B6014-B840-4EC8-96F4-34C08EC303EA">Overview of Hyper-V Extensible Switch Ports</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.30 and later. Supported in NDIS 6.30 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

    ## See Also

        <a href="..\ntddndis\ns-ntddndis-_ndis_switch_port_parameters.md">NDIS_SWITCH_PORT_PARAMETER</a>

<b></b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_STATE enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>