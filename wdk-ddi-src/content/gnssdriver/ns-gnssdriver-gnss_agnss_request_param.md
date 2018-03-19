---
UID: NS:gnssdriver.GNSS_AGNSS_REQUEST_PARAM
title: GNSS_AGNSS_REQUEST_PARAM
author: windows-driver-content
description: This structure defines AGNSS request parameters.
old-location: gnss\gnss_agnss_request_param.htm
old-project: gnss
ms.assetid: 67A1DAEF-13D3-4D47-B10C-0CA30C8EB22F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGNSS_AGNSS_REQUEST_PARAM, GNSS_AGNSS_REQUEST_PARAM, GNSS_AGNSS_REQUEST_PARAM structure [Sensor Devices], PGNSS_AGNSS_REQUEST_PARAM, PGNSS_AGNSS_REQUEST_PARAM structure pointer [Sensor Devices], gnss.gnss_agnss_request_param, gnssdriver/GNSS_AGNSS_REQUEST_PARAM, gnssdriver/PGNSS_AGNSS_REQUEST_PARAM"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	gnssdriver.h
api_name:
-	GNSS_AGNSS_REQUEST_PARAM
product: Windows
targetos: Windows
req.typenames: GNSS_AGNSS_REQUEST_PARAM, *PGNSS_AGNSS_REQUEST_PARAM
---

# GNSS_AGNSS_REQUEST_PARAM structure
This structure defines AGNSS request parameters.

## Syntax
````
typedef struct {
  ULONG                   Size;
  ULONG                   Version;
  GNSS_AGNSS_REQUEST_TYPE RequestType;
  ULONG                   BlobFormat;
} GNSS_AGNSS_REQUEST_PARAM, *PGNSS_AGNSS_REQUEST_PARAM;
````

## Members


`Size`

Structure size.

`Version`

Version number.

`RequestType`

Specifies the type of the request (for example, time injection, blob injection).

`BlobFormat`

If the RequestType is GNSS_AGNSS_BlobInjection, this contains the required  blob format.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | gnssdriver.h |