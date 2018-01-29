---
UID : NE:ks.KSPROPERTY_QUALITY
title : KSPROPERTY_QUALITY
author : windows-driver-content
description : .
old-location : stream\ksproperty_quality.htm
old-project : stream
ms.assetid : 6350A740-BD69-40C3-804A-075F9889865B
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.ksproperty_quality, ks/KSPROPERTY_QUALITY_REPORT, ks/KSPROPERTY_QUALITY, KSPROPERTY_QUALITY enumeration [Streaming Media Devices], KSPROPERTY_QUALITY_ERROR, KSPROPERTY_QUALITY, KSPROPERTY_QUALITY_REPORT, ks/KSPROPERTY_QUALITY_ERROR
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
req.typenames : KSPROPERTY_QUALITY
---

# KSPROPERTY_QUALITY Enumeration


## Syntax
````
typedef enum  { 
  KSPROPERTY_QUALITY_REPORT,
  KSPROPERTY_QUALITY_ERROR
} KSPROPERTY_QUALITY;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_QUALITY_ERROR</td>
<td>Specify if the pin supports quality management.</td>
</tr>

<tr>
<td>KSPROPERTY_QUALITY_REPORT</td>
<td>Specify if the pin supports quality management.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ks.h |