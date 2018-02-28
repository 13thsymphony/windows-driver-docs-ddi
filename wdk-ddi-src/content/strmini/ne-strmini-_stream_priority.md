---
UID: NE:strmini._STREAM_PRIORITY
title: "_STREAM_PRIORITY"
author: windows-driver-content
description: TD.
old-location: stream\stream_priority.htm
old-project: stream
ms.assetid: 790A00A5-1107-4686-B690-80D07B69AF62
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PSTREAM_PRIORITY, Dispatch, High, Low, LowToHigh, PSTREAM_PRIORITY, PSTREAM_PRIORITY enumeration pointer [Streaming Media Devices], STREAM_PRIORITY, STREAM_PRIORITY enumeration [Streaming Media Devices], _STREAM_PRIORITY, stream.stream_priority, strmini/Dispatch, strmini/High, strmini/Low, strmini/LowToHigh, strmini/PSTREAM_PRIORITY, strmini/STREAM_PRIORITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: strmini.h
req.include-header: 
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Strmini.h
api_name:
-	STREAM_PRIORITY
product: Windows
targetos: Windows
req.typenames: STREAM_PRIORITY, *PSTREAM_PRIORITY
req.product: Windows 10 or later.
---

# _STREAM_PRIORITY Enumeration
TD

## Syntax
````
typedef enum _STREAM_PRIORITY { 
  High,
  Dispatch,
  Low,
  LowToHigh                   
} STREAM_PRIORITY, *PSTREAM_PRIORITY
;
````

## Constants

<table>
            
                <tr>
                    <td>Dispatch</td>
                    <td>Medium priority, IRQL equal to dispatch level.</td>
                </tr>
            
                <tr>
                    <td>High</td>
                    <td>Highest priority, IRQL equal to the adapter's ISR.</td>
                </tr>
            
                <tr>
                    <td>Low</td>
                    <td>Lowest priority, IRQL equal to passive or APC level.</td>
                </tr>
            
                <tr>
                    <td>LowToHigh</td>
                    <td>Go from low priority to high priority.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | strmini.h |