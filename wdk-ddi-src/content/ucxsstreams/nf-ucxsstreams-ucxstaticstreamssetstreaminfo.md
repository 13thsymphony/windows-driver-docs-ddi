---
UID: NF:ucxsstreams.UcxStaticStreamsSetStreamInfo
title: UcxStaticStreamsSetStreamInfo function
author: windows-driver-content
description: Sets stream information for each stream enabled by the client driver.
old-location: buses\_ucxstaticstreamssetstreaminfo.htm
old-project: usbref
ms.assetid: 40AE9327-ABB7-4A63-AC90-494E2BC26C08
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: UcxStaticStreamsSetStreamInfo, UcxStaticStreamsSetStreamInfo method [Buses], buses._ucxstaticstreamssetstreaminfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxsstreams.h
req.include-header: Ucxclass.h, Ucxstreams.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
-	COM
api_location:
-	ucxsstreams.h
api_name:
-	UcxStaticStreamsSetStreamInfo
product: Windows
targetos: Windows
req.typenames: UCX_ROOTHUB_CONFIG, *PUCX_ROOTHUB_CONFIG
req.product: Windows 10 or later.
---


# UcxStaticStreamsSetStreamInfo function
Sets stream information for each stream enabled by the client driver.

## Syntax

```
void UcxStaticStreamsSetStreamInfo(
  UCXSSTREAMS  StaticStreams,
  PSTREAM_INFO StreamInfo
);
```

## Parameters

`StaticStreams`

The handle to the Static Streams object just been created.

`StreamInfo`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt188032">STREAM_INFO</a> structure that contains static stream-related information.


## Return Value

This method does not return a value.

## Remarks

The client driver must call this method from its implementation of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> event callback . 
    This method must be called for the number of streams on the endpoint. 

For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/mt187830">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxsstreams.h (include Ucxclass.h, Ucxstreams.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>