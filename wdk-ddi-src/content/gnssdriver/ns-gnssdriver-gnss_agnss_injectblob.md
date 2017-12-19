---
UID: NS.GNSSDRIVER.GNSS_AGNSS_INJECTBLOB
title: GNSS_AGNSS_INJECTBLOB
author: windows-driver-content
description: This structure defines the format for AGNSS extended ephemeris injection.
old-location: sensors\gnss_agnss_injectblob.htm
old-project: sensors
ms.assetid: DAC91C40-C9B3-433C-AA64-CE4C021CD8C5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_AGNSS_INJECTBLOB, *PGNSS_AGNSS_INJECTBLOB, GNSS_AGNSS_INJECTBLOB, PGNSS_AGNSS_INJECTBLOB
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
req.alt-api: GNSS_AGNSS_INJECTBLOB
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
---

# GNSS_AGNSS_INJECTBLOB structure



## -description
This structure defines the format for AGNSS extended ephemeris injection.



## -syntax

````
typedef struct {
  ULONG Size;
  ULONG Version;
  ULONG BlobOui;
  ULONG BlobVersion;
  ULONG AgnssFormat;
  ULONG BlobSize;
  BYTE  BlobData[ANYSIZE_ARRAY];
} GNSS_AGNSS_INJECTBLOB, *PGNSS_AGNSS_INJECTBLOB;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field BlobOui

This field indicates the 3-byte OUI of silicon vendor or device maker.


### -field BlobVersion

Version of the blob from the same vendor.


### -field AgnssFormat

Data format of the blob.

The formats are defined as macros (GNSS_AGNSSFORMAT_*).


### -field BlobSize

Size of the blob data in bytes.


### -field BlobData[ANYSIZE_ARRAY]

This field defines the start of the blob data.

The structure only contains the first byte of the blob data. The rest of the blob data is saved right after the structure in the memory. The size of the blob  is indicated by BlobSize.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>