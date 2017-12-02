---
UID: NE.rilapitypes.RILREMOTEPARTYINFOVALUEPARAM~r1
title: RILREMOTEPARTYINFOVALUEPARAM
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilremotepartyinfovalueparam_2.htm
old-project: netvista
ms.assetid: eeea39eb-898a-47fe-befe-39c95dd1fc90
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RIL_WritePhonebookEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILREMOTEPARTYINFOVALUEPARAM
req.alt-loc: rilapitypes.h
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
req.iface: 
req.product: Windows 10 or later.
---

# RILREMOTEPARTYINFOVALUEPARAM enumeration



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. </p>


## -syntax

````
typedef enum _RILREMOTEPARTYINFOVALUEPARAM { 
  RIL_PARAM_RPI_ADDRESS,
  RIL_PARAM_RPI_SUBADDRESS,
  RIL_PARAM_RPI_DESCRIPTION,
  RIL_PARAM_RPI_NUM_PRES_IND,
  RIL_PARAM_RPI_NAME_PRES_IND,
  RIL_PARAM_RPI_ID,
  RIL_PARAM_RPI_ALL
} RILREMOTEPARTYINFOVALUEPARAM;
````


## -enum-fields
<dl>

### -field RIL_PARAM_RPI_ADDRESS

<dd></dd>

### -field RIL_PARAM_RPI_SUBADDRESS

<dd></dd>

### -field RIL_PARAM_RPI_DESCRIPTION

<dd></dd>

### -field RIL_PARAM_RPI_NUM_PRES_IND

<dd></dd>

### -field RIL_PARAM_RPI_NAME_PRES_IND

<dd></dd>

### -field RIL_PARAM_RPI_ID

<dd></dd>

### -field RIL_PARAM_RPI_ALL

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>