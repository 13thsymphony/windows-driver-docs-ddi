---
UID: NS.KS.PBUS_INTERFACE_MEDIUMS
title: PBUS_INTERFACE_MEDIUMS
author: windows-driver-content
description: .
old-location: stream\bus_interface_mediums.htm
old-project: stream
ms.assetid: 0A2D1D8F-8C82-4335-9FBF-4515A8DC20C1
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: PBUS_INTERFACE_MEDIUMS, *PBUS_INTERFACE_MEDIUMS, BUS_INTERFACE_MEDIUMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: BUS_INTERFACE_MEDIUMS
req.alt-loc: Ks.h
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
---

# PBUS_INTERFACE_MEDIUMS structure



## -description



## -syntax

````
typedef struct {
  INTERFACE           Interface;
  PFNQUERYMEDIUMSLIST QueryMediumsList;
} BUS_INTERFACE_MEDIUMS, *PBUS_INTERFACE_MEDIUMS;
````


## -struct-fields

### -field Interface

Specifies the standard interface header.

### -field QueryMediumsList

Specifies the interface definition.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ks.h</dt>
</dl>
</td>
</tr>
</table>