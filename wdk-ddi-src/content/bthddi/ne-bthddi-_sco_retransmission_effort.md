---
UID : NE:bthddi._SCO_RETRANSMISSION_EFFORT
title : _SCO_RETRANSMISSION_EFFORT
author : windows-driver-content
description : The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a SCO channel.
old-location : bltooth\sco_retransmission_effort.htm
old-project : bltooth
ms.assetid : bf466384-bf13-42cc-a02d-ef880cac4c02
ms.author : windowsdriverdev
ms.date : 12/21/2017
ms.keywords : _SCO_RETRANSMISSION_EFFORT, SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : bthddi.h
req.include-header : Bthddi.h
req.target-type : Windows
req.target-min-winverclnt : Versions: Supported in Windows Vista, and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : SCO_RETRANSMISSION_EFFORT
req.alt-loc : bthddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
req.typenames : SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT
---

# _SCO_RETRANSMISSION_EFFORT Enumeration
The SCO_RETRANSMISSION_EFFORT enumeration type is used to determine the retransmission policies of a
  SCO channel.

## Syntax
````
typedef enum _SCO_RETRANSMISSION_EFFORT { 
  SCO_RETRANSMISSION_NONE          = 0x00,
  SCO_RETRANSMISSION_MIN1_POWER    = 0x01,
  SCO_RETRANSMISSION_MIN1_QUALITY  = 0x02,
  SCO_RETRANSMISSION_DONT_CARE     = 0xFF
} SCO_RETRANSMISSION_EFFORT, *PSCO_RETRANSMISSION_EFFORT;
````

## Constants

<table>

<tr>
<td>SCO_RETRANSMISSION_DONT_CARE</td>
<td>The profile driver specifies that retransmissions can occur, but are not required.</td>
</tr>

<tr>
<td>SCO_RETRANSMISSION_MIN1_POWER</td>
<td>The profile driver specifies that there should be at least one retransmission on the channel. Any
     retransmissions that are performed should be optimized for power consumption.</td>
</tr>

<tr>
<td>SCO_RETRANSMISSION_MIN1_QUALITY</td>
<td>The profile driver specifies that there should be at least one retransmission on the channel. Any
     retransmissions that are performed should be optimized for link quality.</td>
</tr>

<tr>
<td>SCO_RETRANSMISSION_NONE</td>
<td>The profile driver specifies that there should be no retransmissions on the channel.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | bthddi.h (include Bthddi.h) |