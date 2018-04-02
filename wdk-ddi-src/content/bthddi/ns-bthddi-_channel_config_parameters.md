---
UID: NS:bthddi._CHANNEL_CONFIG_PARAMETERS
title: "_CHANNEL_CONFIG_PARAMETERS"
author: windows-driver-content
description: The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound directions of a L2CAP channel.
old-location: bltooth\channel_config_parameters.htm
old-project: bltooth
ms.assetid: c2201e3c-c680-4a22-adf5-5131fb138066
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCHANNEL_CONFIG_PARAMETERS, CHANNEL_CONFIG_PARAMETERS, CHANNEL_CONFIG_PARAMETERS structure [Bluetooth Devices], PCHANNEL_CONFIG_PARAMETERS, PCHANNEL_CONFIG_PARAMETERS structure pointer [Bluetooth Devices], _CHANNEL_CONFIG_PARAMETERS, bltooth.channel_config_parameters, bth_structs_c5360d7a-eb76-4b27-8507-8de862737a06.xml, bthddi/CHANNEL_CONFIG_PARAMETERS, bthddi/PCHANNEL_CONFIG_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	CHANNEL_CONFIG_PARAMETERS
product: Windows
targetos: Windows
req.typenames: CHANNEL_CONFIG_PARAMETERS, *PCHANNEL_CONFIG_PARAMETERS
---

# _CHANNEL_CONFIG_PARAMETERS structure
The CHANNEL_CONFIG_PARAMETERS structure contains configuration parameters for inbound and outbound
  directions of a L2CAP channel.

## Syntax
```
typedef struct _CHANNEL_CONFIG_PARAMETERS {
  ULONG                Flags;
  CO_MTU               Mtu;
  CO_FLUSHTO           FlushTO;
  ULONG                NumExtraOptions;
  PL2CAP_CONFIG_OPTION ExtraOptions;
  L2CAP_FLOWSPEC       Flow;
} *PCHANNEL_CONFIG_PARAMETERS, CHANNEL_CONFIG_PARAMETERS;
```

## Members


`Flags`

A flag or combination of flags that specifies which members of this structure contain data. Valid
     flag values are listed in the following table.
     

<table>
<tr>
<th>Flag</th>
<th>Description</th>
</tr>
<tr>
<td>
CFG_EXTRA

</td>
<td>
If set, the 
        <b>ExtraOptions</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_FLUSHTO

</td>
<td>
If set, the 
        <b>FlushTO</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_MTU

</td>
<td>
If set, the 
        <b>Mtu</b> member contains data.

</td>
</tr>
<tr>
<td>
CFG_QOS

</td>
<td>
If set, the 
        <b>Flow</b> member contains data.

</td>
</tr>
</table>

`Mtu`

The message transfer units for the specified channel direction.

`FlushTO`

The flush timeout for the specified channel direction.

`NumExtraOptions`

The number of items specified in the array that is specified in the 
     <b>ExtraOptions</b> member.

`ExtraOptions`

The number of items specified in the array that is specified in the 
     <b>ExtraOptions</b> member.

`Flow`

The QoS settings for the specified channel direction.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536757">L2CAP_CONFIG_OPTION</a>