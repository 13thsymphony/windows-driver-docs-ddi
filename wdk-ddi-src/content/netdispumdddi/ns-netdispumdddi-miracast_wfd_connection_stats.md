---
UID : NS:netdispumdddi.MIRACAST_WFD_CONNECTION_STATS
title : MIRACAST_WFD_CONNECTION_STATS
author : windows-driver-content
description : Contains bit rate info on the Wi-Fi Direct connection.
old-location : display\miracast_wfd_connection_stats.htm
old-project : display
ms.assetid : 3d5dd27f-8d0e-46e8-adbd-139db322cf6e
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : netdispumdddi/MIRACAST_WFD_CONNECTION_STATS, display.miracast_wfd_connection_stats, MIRACAST_WFD_CONNECTION_STATS structure [Display Devices], MIRACAST_WFD_CONNECTION_STATS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : netdispumdddi.h
req.include-header : Netdispumdddi.h
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : MIRACAST_WFD_CONNECTION_STATS
---

# MIRACAST_WFD_CONNECTION_STATS structure
Contains bit rate info on the Wi-Fi Direct connection.

## Syntax
````
typedef struct {
  UINT64 CurrentBitRate;
  UINT64 LocalMaxBitRate;
  UINT64 RemoteMaxBitRate;
} MIRACAST_WFD_CONNECTION_STATS;
````

## Members


`CurrentBitRate`

The bit rate, in bits per second, that the operating system recommends that the audio/video encoder uses.

`LocalMaxBitRate`

The maximum bit rate, in bits per second, that the local Wi-Fi Direct hardware can support.

`RemoteMaxBitRate`

The maximum bit rate, in bits per second, that the Miracast sink hardware can support.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |