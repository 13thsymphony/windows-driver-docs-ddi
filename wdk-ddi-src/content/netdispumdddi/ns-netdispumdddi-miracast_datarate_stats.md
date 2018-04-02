---
UID: NS:netdispumdddi.MIRACAST_DATARATE_STATS
title: MIRACAST_DATARATE_STATS
author: windows-driver-content
description: Contains info used in the wireless display (Miracast) pfnDataRateNotify function about the audio/video encoder bit rate and failed or retried Wi-Fi frames.
old-location: display\miracast_datarate_stats.htm
old-project: display
ms.assetid: d4249b81-0ee7-49dd-9886-cdc5842f02d8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: MIRACAST_DATARATE_STATS, MIRACAST_DATARATE_STATS structure [Display Devices], display.miracast_datarate_stats, netdispumdddi/MIRACAST_DATARATE_STATS
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Netdispumdddi.h
api_name:
-	MIRACAST_DATARATE_STATS
product: Windows
targetos: Windows
req.typenames: MIRACAST_DATARATE_STATS
---

# MIRACAST_DATARATE_STATS structure
Contains info used in the wireless display (Miracast) <a href="https://msdn.microsoft.com/5eb004d1-7cf8-45a3-aad5-2932b1a83bb8">pfnDataRateNotify</a> function about the audio/video encoder bit rate and failed or retried Wi-Fi frames.

## Syntax
```
typedef struct MIRACAST_DATARATE_STATS {
  UINT64 EncoderBitRate;
  UINT64 CurrentMaxTxDataRate;
  UINT64 TransmittedFrameCount;
  UINT64 FailedFrameCount;
  UINT64 RetriedFrameCount;
  UINT64 MultipleRetryFrameCount;
};
```

## Members


`EncoderBitRate`

The bit rate, in bits per second, that the operating system recommends that the audio/video encoder uses.

`CurrentMaxTxDataRate`

The theoretical maximum speed, in bits per second, reported by the Wi-Fi driver.

`TransmittedFrameCount`

The total number of Wi-Fi frames that were sent with zero retries since the previous time step.

`FailedFrameCount`

The total number of Wi-Fi frames that exhausted the maximum number of retries since the previous time step.

`RetriedFrameCount`

The total number of Wi-Fi frames that succeeded after a single retry since the previous time step.

`MultipleRetryFrameCount`

The total number of Wi-Fi frames that succeeded after more than one retry since the previous time step.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | netdispumdddi.h (include Netdispumdddi.h) |