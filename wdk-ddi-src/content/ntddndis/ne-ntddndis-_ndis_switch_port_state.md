---
UID: NE.ntddndis._NDIS_SWITCH_PORT_STATE
title: _NDIS_SWITCH_PORT_STATE
author: windows-driver-content
description: The NDIS_SWITCH_PORT_STATE enumeration specifies the current state of the Hyper-V extensible switch port.
old-location: netvista\ndis_switch_port_state.htm
old-project: netvista
ms.assetid: BEF37F32-036D-4381-93B3-C159ABCFC3F9
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_SWITCH_PORT_STATE, NDIS_SWITCH_PORT_STATE
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
req.alt-api: NDIS_SWITCH_PORT_STATE
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

# _NDIS_SWITCH_PORT_STATE enumeration



## -description
The <b>NDIS_SWITCH_PORT_STATE</b> enumeration specifies the current state of the Hyper-V extensible switch port. 


## -syntax

````
typedef enum _NDIS_SWITCH_PORT_STATE { 
  NdisSwitchPortStateUnknown   = 0,
  NdisSwitchPortStateCreated   = 1,
  NdisSwitchPortStateTeardown  = 2,
  NdisSwitchPortStateDeleted   = 3
} NDIS_SWITCH_PORT_STATE;
````


## -enum-fields

### -field NdisSwitchPortStateUnknown

This value specifies an undefined port state. This value is unused.

### -field NdisSwitchPortStateCreated

This value specifies that the port is in the created state. 

### -field NdisSwitchPortStateTeardown

This value specifies that the port is being torn down.

### -field NdisSwitchPortStateDeleted

This value specifies that the port has been deleted. 

## -remarks
The <b>PortState</b>  member of the <a href="netvista.ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETER</a> structure is an <b>NDIS_SWITCH_PORT_STATE</b> enumeration data type. 


For more information about extensible switch port states, see <a href="netvista.overview_of_hyper_v_extensible_switch_ports">Overview of Hyper-V Extensible Switch Ports</a>. 


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
<a href="netvista.ndis_switch_port_parameters">NDIS_SWITCH_PORT_PARAMETER</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_SWITCH_PORT_STATE enumeration%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
