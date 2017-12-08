---
UID: NS.gnssdriver.PGNSS_AGNSS_INJECTPOSITION
title: PGNSS_AGNSS_INJECTPOSITION
author: windows-driver-content
description: This structure defines the format for AGNSS position injection.
old-location: sensors\gnss_agnss_injectposition.htm
old-project: sensors
ms.assetid: 1FB73F94-F8F3-409F-8B34-3CD303512AD0
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_AGNSS_INJECTPOSITION, GNSS_AGNSS_INJECTPOSITION, *PGNSS_AGNSS_INJECTPOSITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_AGNSS_INJECTPOSITION
req.alt-loc: gnssdriver.h
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
---

# PGNSS_AGNSS_INJECTPOSITION structure



## -description
<p>This structure defines the format for AGNSS position injection.</p>


## -syntax

````
typedef struct {
  ULONG                 Size;
  ULONG                 Version;
  ULONG                 Age;
  GNSS_FIXDATA_BASIC    BasicData;
  GNSS_FIXDATA_ACCURACY AccuracyData;
} GNSS_AGNSS_INJECTPOSITION, *PGNSS_AGNSS_INJECTPOSITION;
````


## -struct-fields
<dl>

### -field Size

<dd>
<p>Structure size.</p>
</dd>

### -field Version

<dd>
<p>Version number.</p>
</dd>

### -field Age

<dd>
<p>Indicates how long the position has been aged in seconds.</p>
</dd>

### -field BasicData

<dd>
<p>Position data.</p>
</dd>

### -field AccuracyData

<dd>
<p>Position accuracy.</p>
</dd>
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
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>