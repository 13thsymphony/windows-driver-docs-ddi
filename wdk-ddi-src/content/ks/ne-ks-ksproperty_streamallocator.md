---
UID : NE:ks.KSPROPERTY_STREAMALLOCATOR
title : KSPROPERTY_STREAMALLOCATOR
author : windows-driver-content
description : "."
old-location : stream\ksproperty_streamallocator.htm
old-project : stream
ms.assetid : 4731864F-01B3-42CB-A1D4-C82FDD1DCBBE
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : ks/KSPROPERTY_STREAMALLOCATOR, KSPROPERTY_STREAMALLOCATOR enumeration [Streaming Media Devices], ks/KSPROPERTY_STREAMALLOCATOR_STATUS, stream.ksproperty_streamallocator, KSPROPERTY_STREAMALLOCATOR, KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE, ks/KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE, KSPROPERTY_STREAMALLOCATOR_STATUS
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
req.typenames : KSPROPERTY_STREAMALLOCATOR
---

# KSPROPERTY_STREAMALLOCATOR Enumeration


## Syntax
````
typedef enum  { 
  KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE,
  KSPROPERTY_STREAMALLOCATOR_STATUS
} KSPROPERTY_STREAMALLOCATOR;
````

## Constants

<table>

<tr>
<td>KSPROPERTY_STREAMALLOCATOR_FUNCTIONTABLE</td>
<td>Specify to retrieve the function table of the allocator.</td>
</tr>

<tr>
<td>KSPROPERTY_STREAMALLOCATOR_STATUS</td>
<td>Specify to retrieve the current status of the specified allocator.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h |