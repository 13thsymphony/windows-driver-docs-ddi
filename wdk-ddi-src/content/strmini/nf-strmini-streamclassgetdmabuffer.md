---
UID: NF:strmini.StreamClassGetDmaBuffer
title: StreamClassGetDmaBuffer function
author: windows-driver-content
description: The StreamClassGetDmaBuffer routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.
old-location: stream\streamclassgetdmabuffer.htm
old-project: stream
ms.assetid: 1b778d94-55e6-4a5f-aa77-739bcf9a8041
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: StreamClassGetDmaBuffer, StreamClassGetDmaBuffer routine [Streaming Media Devices], strclass-routines_d010423c-9c48-4dee-8ca3-f4b2854d14c9.xml, stream.streamclassgetdmabuffer, strmini/StreamClassGetDmaBuffer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: strmini.h
req.include-header: Strmini.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Stream.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Stream.lib
-	Stream.dll
api_name:
-	StreamClassGetDmaBuffer
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---


# StreamClassGetDmaBuffer function
The <b>StreamClassGetDmaBuffer</b> routine returns a pointer to the DMA buffer that the class driver allocates for the minidriver.

## Syntax

````
PVOID StreamClassGetDmaBuffer(
  _In_ PVOID HwDeviceExtension
);
````

## Parameters

`HwDeviceExtension`

Pointer to the minidriver's device extension. The minidriver specifies the size of this buffer in the <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure it passes when it registers itself via <a href="https://msdn.microsoft.com/library/windows/hardware/ff568263">StreamClassRegisterMinidriver</a>. The class driver then passes pointers to the buffer in the <b>HwDeviceExtension</b> member of the <a href="..\strmini\ns-strmini-_hw_stream_request_block.md">HW_STREAM_REQUEST_BLOCK</a>, <a href="..\strmini\ns-strmini-_hw_stream_object.md">HW_STREAM_OBJECT</a>, <a href="..\strmini\ns-strmini-_hw_time_context.md">HW_TIME_CONTEXT</a>, and <a href="..\strmini\ns-strmini-_port_configuration_information.md">PORT_CONFIGURATION_INFORMATION</a> structures it passes to the minidriver.


## Return Value

<b>StreamClassGetDmaBuffer</b> returns a pointer to the DMA buffer.

## Remarks

The minidriver specifies the size of the DMA buffer in the <b>DmaBufferSize</b> member of its <a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a> structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | strmini.h (include Strmini.h) |
| **Library** | Stream.lib |

## See Also

<a href="..\strmini\ns-strmini-_hw_initialization_data.md">HW_INITIALIZATION_DATA</a>