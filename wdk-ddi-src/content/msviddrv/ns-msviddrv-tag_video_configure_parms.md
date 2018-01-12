---
UID: NS:msviddrv.tag_video_configure_parms
title: tag_video_configure_parms
author: windows-driver-content
description: .
old-location: stream\videoconfigparms.htm
old-project: stream
ms.assetid: 58FE3B56-AFC6-46DE-BBE1-CCFA8FF1390A
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tag_video_configure_parms, *LPVIDEOCONFIGPARMS, VIDEOCONFIGPARMS
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
req.alt-api: VIDEOCONFIGPARMS
req.alt-loc: Msviddrv.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: *LPVIDEOCONFIGPARMS, VIDEOCONFIGPARMS
---

# tag_video_configure_parms structure



## -description




## -syntax

````
typedef struct tag_video_configure_parms {
  LPDWORD lpdwReturn;
  LPVOID  lpData1;
  DWORD   dwSize1;
  LPVOID  lpData2;
  DWORD   dwSize2;
} VIDEOCONFIGPARMS, *LPVIDEOCONFIGPARMS;
````


## -struct-fields

### -field lpdwReturn

Specifies the return parameter from the configure MSG.


### -field lpData1

Specifies a pointer to data 1.


### -field dwSize1

Specifies the size of data buffer 1.


### -field lpData2

Specifies a pointer to data 2.


### -field dwSize2

Specifies the size of data buffer 2.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Msviddrv.h</dt>
</dl>
</td>
</tr>
</table>