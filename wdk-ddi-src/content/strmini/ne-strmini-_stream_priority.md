---
UID: NE.strmini._STREAM_PRIORITY
title: _STREAM_PRIORITY
author: windows-driver-content
description: TD.
old-location: stream\stream_priority.htm
old-project: stream
ms.assetid: 790A00A5-1107-4686-B690-80D07B69AF62
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _STREAM_PRIORITY, STREAM_PRIORITY, *PSTREAM_PRIORITY
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
req.alt-api: STREAM_PRIORITY
req.alt-loc: Strmini.h
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
req.product: Windows 10 or later.
---

# _STREAM_PRIORITY enumeration



## -description
TD



## -syntax

````
typedef enum _STREAM_PRIORITY { 
  High,
  Dispatch,
  Low,
  LowToHigh                   
} STREAM_PRIORITY, *PSTREAM_PRIORITY
;
````


## -enum-fields

### -field High

Highest priority, IRQL equal to the adapter's ISR.


### -field Dispatch

Medium priority, IRQL equal to dispatch level.


### -field Low

Lowest priority, IRQL equal to passive or APC level.


### -field LowToHigh                   

Go from low priority to high priority.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Strmini.h</dt>
</dl>
</td>
</tr>
</table>