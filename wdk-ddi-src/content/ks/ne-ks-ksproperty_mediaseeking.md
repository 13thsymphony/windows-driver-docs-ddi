---
UID : NE:ks.KSPROPERTY_MEDIASEEKING
title : KSPROPERTY_MEDIASEEKING
author : windows-driver-content
description : .
old-location : stream\ksproperty_mediaseeking.htm
old-project : stream
ms.assetid : 9B9C308B-7D0B-4549-9EE5-2E53B0B8946C
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : KSPROPERTY_MEDIASEEKING, KSPROPERTY_MEDIASEEKING
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ks.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : KSPROPERTY_MEDIASEEKING
req.alt-loc : Ks.h
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
req.typenames : KSPROPERTY_MEDIASEEKING
---

# KSPROPERTY_MEDIASEEKING Enumeration


## Syntax
````
typedef enum  { 
  KSPROPERTY_MEDIASEEKING_CAPABILITIES,
  KSPROPERTY_MEDIASEEKING_FORMATS,
  KSPROPERTY_MEDIASEEKING_TIMEFORMAT,
  KSPROPERTY_MEDIASEEKING_POSITION,
  KSPROPERTY_MEDIASEEKING_STOPPOSITION,
  KSPROPERTY_MEDIASEEKING_POSITIONS,
  KSPROPERTY_MEDIASEEKING_DURATION,
  KSPROPERTY_MEDIASEEKING_AVAILABLE,
  KSPROPERTY_MEDIASEEKING_PREROLL,
  KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT
} KSPROPERTY_MEDIASEEKING;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_MEDIASEEKING_AVAILABLE</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_CAPABILITIES</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_CONVERTTIMEFORMAT</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_DURATION</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_FORMATS</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_POSITION</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_POSITIONS</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_PREROLL</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_STOPPOSITION</td>
<td></td>
</tr>

<tr>
<td>KSPROPERTY_MEDIASEEKING_TIMEFORMAT</td>
<td></td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |