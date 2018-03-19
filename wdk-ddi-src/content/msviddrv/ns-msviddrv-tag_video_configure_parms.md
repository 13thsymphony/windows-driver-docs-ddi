---
UID: NS:msviddrv.tag_video_configure_parms
title: tag_video_configure_parms
author: windows-driver-content
description: "."
old-location: stream\videoconfigparms.htm
old-project: stream
ms.assetid: 58FE3B56-AFC6-46DE-BBE1-CCFA8FF1390A
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*LPVIDEOCONFIGPARMS, LPVIDEOCONFIGPARMS, LPVIDEOCONFIGPARMS structure pointer [Streaming Media Devices], VIDEOCONFIGPARMS, VIDEOCONFIGPARMS structure [Streaming Media Devices], msviddrv/LPVIDEOCONFIGPARMS, msviddrv/VIDEOCONFIGPARMS, stream.videoconfigparms, tag_video_configure_parms"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: msviddrv.h
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Msviddrv.h
api_name:
-	VIDEOCONFIGPARMS
product: Windows
targetos: Windows
req.typenames: VIDEOCONFIGPARMS, *LPVIDEOCONFIGPARMS
---

# tag_video_configure_parms structure


## Syntax
````
typedef struct tag_video_configure_parms {
  LPDWORD lpdwReturn;
  LPVOID  lpData1;
  DWORD   dwSize1;
  LPVOID  lpData2;
  DWORD   dwSize2;
} VIDEOCONFIGPARMS, *LPVIDEOCONFIGPARMS;
````

## Members


`lpdwReturn`

Specifies the return parameter from the configure MSG.

`lpData1`

Specifies a pointer to data 1.

`dwSize1`

Specifies the size of data buffer 1.

`lpData2`

Specifies a pointer to data 2.

`dwSize2`

Specifies the size of data buffer 2.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | msviddrv.h |