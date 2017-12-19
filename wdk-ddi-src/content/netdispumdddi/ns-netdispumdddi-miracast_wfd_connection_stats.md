---
UID: NS.NETDISPUMDDDI.MIRACAST_WFD_CONNECTION_STATS
title: MIRACAST_WFD_CONNECTION_STATS
author: windows-driver-content
description: Contains bit rate info on the Wi-Fi Direct connection.
old-location: display\miracast_wfd_connection_stats.htm
old-project: display
ms.assetid: 3d5dd27f-8d0e-46e8-adbd-139db322cf6e
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: MIRACAST_WFD_CONNECTION_STATS, MIRACAST_WFD_CONNECTION_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: netdispumdddi.h
req.include-header: Netdispumdddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MIRACAST_WFD_CONNECTION_STATS
req.alt-loc: Netdispumdddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# MIRACAST_WFD_CONNECTION_STATS structure



## -description
Contains bit rate info on the Wi-Fi Direct connection.



## -syntax

````
typedef struct {
  UINT64 CurrentBitRate;
  UINT64 LocalMaxBitRate;
  UINT64 RemoteMaxBitRate;
} MIRACAST_WFD_CONNECTION_STATS;
````


## -struct-fields

### -field CurrentBitRate

The bit rate, in bits per second, that the operating system recommends that the audio/video encoder uses.


### -field LocalMaxBitRate

The maximum bit rate, in bits per second, that the local Wi-Fi Direct hardware can support.


### -field RemoteMaxBitRate

The maximum bit rate, in bits per second, that the Miracast sink hardware can support.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Netdispumdddi.h (include Netdispumdddi.h)</dt>
</dl>
</td>
</tr>
</table>