---
UID: NE.gnssdriver.GNSS_AGNSS_REQUEST_TYPE
title: GNSS_AGNSS_REQUEST_TYPE
author: windows-driver-content
description: This enumeration indicates the type of AGNSS injection request represented by the GNSS_AGNSS_REQUEST_PARAM structure.
old-location: sensors\gnss_agnss_request_type.htm
old-project: sensors
ms.assetid: 31293354-D68B-475F-91BD-0504129207A5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GNSS_AGNSS_REQUEST_TYPE, GNSS_AGNSS_REQUEST_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_AGNSS_REQUEST_TYPE
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
req.irql: <= DISPATCH_LEVEL
---

# GNSS_AGNSS_REQUEST_TYPE enumeration



## -description
This enumeration indicates the type of AGNSS injection request represented by the <a href="..\gnssdriver\ns-gnssdriver-gnss_agnss_request_param.md">GNSS_AGNSS_REQUEST_PARAM</a> structure.



## -syntax

````
typedef enum  { 
  GNSS_AGNSS_TimeInjection      = 0x01,
  GNSS_AGNSS_PositionInjection  = 0x02,
  GNSS_AGNSS_BlobInjection      = 0x03
} GNSS_AGNSS_REQUEST_TYPE;
````


## -enum-fields

### -field GNSS_AGNSS_TimeInjection

Indicates the injection request is for time injection.


### -field GNSS_AGNSS_PositionInjection

Indicates the injection request is for position injection.


### -field GNSS_AGNSS_BlobInjection

Indicates the injection request is for blob injection.


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