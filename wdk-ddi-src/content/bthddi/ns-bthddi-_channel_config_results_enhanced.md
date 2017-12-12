---
UID: NS.BTHDDI._CHANNEL_CONFIG_RESULTS_ENHANCED
title: _CHANNEL_CONFIG_RESULTS_ENHANCED
author: windows-driver-content
description: The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel.
old-location: bltooth\channel_config_results_enhanced.htm
old-project: bltooth
ms.assetid: E7A2FC77-86B0-4990-93DC-2A04E33A426C
ms.author: windowsdriverdev
ms.date: 11/27/2017
ms.keywords: _CHANNEL_CONFIG_RESULTS_ENHANCED, *PCHANNEL_CONFIG_RESULTS_ENHANCED, CHANNEL_CONFIG_RESULTS_ENHANCED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions: Supported in Windows 8 and later versions of Windows
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CHANNEL_CONFIG_RESULTS_ENHANCED
req.alt-loc: Bthddi.h
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
---

# _CHANNEL_CONFIG_RESULTS_ENHANCED structure



## -description
The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel.



## -syntax

````
typedef struct _CHANNEL_CONFIG_RESULTS_ENHANCED {
  CHANNEL_CONFIG_PARAMETERS_ENHANCED Params;
  ULONG                              ExtraOptionsBufferSize;
} CHANNEL_CONFIG_RESULTS_ENHANCED, *PCHANNEL_CONFIG_RESULTS_ENHANCED;
````


## -struct-fields

### -field Params

Channel parameters for the given direction of the channel


### -field ExtraOptionsBufferSize

Amount of buffer required to retrieve the current extra options for the given direction


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Versions: Supported in Windows 8 and later versions of Windows

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Bthddi.h (include Bthddi.h)</dt>
</dl>
</td>
</tr>
</table>