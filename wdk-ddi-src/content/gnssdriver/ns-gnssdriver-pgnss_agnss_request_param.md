---
UID: NS.GNSSDRIVER.PGNSS_AGNSS_REQUEST_PARAM
title: PGNSS_AGNSS_REQUEST_PARAM
author: windows-driver-content
description: This structure defines AGNSS request parameters.
old-location: sensors\gnss_agnss_request_param.htm
old-project: sensors
ms.assetid: 67A1DAEF-13D3-4D47-B10C-0CA30C8EB22F
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PGNSS_AGNSS_REQUEST_PARAM, GNSS_AGNSS_REQUEST_PARAM, *PGNSS_AGNSS_REQUEST_PARAM
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
req.alt-api: GNSS_AGNSS_REQUEST_PARAM
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

# PGNSS_AGNSS_REQUEST_PARAM structure



## -description
This structure defines AGNSS request parameters.



## -syntax

````
typedef struct {
  ULONG                   Size;
  ULONG                   Version;
  GNSS_AGNSS_REQUEST_TYPE RequestType;
  ULONG                   BlobFormat;
} GNSS_AGNSS_REQUEST_PARAM, *PGNSS_AGNSS_REQUEST_PARAM;
````


## -struct-fields

### -field Size

Structure size.


### -field Version

Version number.


### -field RequestType

Specifies the type of the request (for example, time injection, blob injection).


### -field BlobFormat

If the RequestType is GNSS_AGNSS_BlobInjection, this contains the required  blob format.


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