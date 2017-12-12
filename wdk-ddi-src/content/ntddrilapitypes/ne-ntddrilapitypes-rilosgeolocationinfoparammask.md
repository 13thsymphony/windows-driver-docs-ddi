---
UID: NE.ntddrilapitypes.RILOSGEOLOCATIONINFOPARAMMASK
title: RILOSGEOLOCATIONINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilosgeolocationinfoparammask.htm
old-project: netvista
ms.assetid: 9a155a35-d0fc-45bd-94fb-16200bcab1a6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILOSGEOLOCATIONINFOPARAMMASK, RILOSGEOLOCATIONINFOPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILOSGEOLOCATIONINFOPARAMMASK
req.alt-loc: ntddrilapitypes.h
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

# RILOSGEOLOCATIONINFOPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILOSGEOLOCATIONINFOPARAMMASK { 
  RIL_PARAM_OSGEOLOCATIONINFO_SIZE,
  RIL_PARAM_OSGEOLOCATIONINFO_LATLONG,
  RIL_PARAM_OSGEOLOCATIONINFO_ALTITUDE,
  RIL_PARAM_OSGEOLOCATIONINFO_ACCURACY,
  RIL_PARAM_OSGEOLOCATIONINFO_MASK,
  RIL_PARAM_OSGEOLOCATIONINFO_ADDRESS1,
  RIL_PARAM_OSGEOLOCATIONINFO_ADDRESS2,
  RIL_PARAM_OSGEOLOCATIONINFO_CITY,
  RIL_PARAM_OSGEOLOCATIONINFO_STATE,
  RIL_PARAM_OSGEOLOCATIONINFO_COUNTRY,
  RIL_PARAM_OSGEOLOCATIONINFO_POSTALCODE,
  RIL_PARAM_OSGEOLOCATIONINFO_COUNTRYCODE,
  RIL_PARAM_OSGEOLOCATIONINFO_REGIONCODE,
  RIL_PARAM_OSGEOLOCATIONINFO_FORMATTEDADDRESS,
  RIL_PARAM_OSGEOLOCATIONINFO_TIMESTAMP,
  RIL_PARAM_OSGEOLOCATIONINFO_ALL
} RILOSGEOLOCATIONINFOPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_OSGEOLOCATIONINFO_SIZE


### -field RIL_PARAM_OSGEOLOCATIONINFO_LATLONG


### -field RIL_PARAM_OSGEOLOCATIONINFO_ALTITUDE


### -field RIL_PARAM_OSGEOLOCATIONINFO_ACCURACY


### -field RIL_PARAM_OSGEOLOCATIONINFO_MASK


### -field RIL_PARAM_OSGEOLOCATIONINFO_ADDRESS1


### -field RIL_PARAM_OSGEOLOCATIONINFO_ADDRESS2


### -field RIL_PARAM_OSGEOLOCATIONINFO_CITY


### -field RIL_PARAM_OSGEOLOCATIONINFO_STATE


### -field RIL_PARAM_OSGEOLOCATIONINFO_COUNTRY


### -field RIL_PARAM_OSGEOLOCATIONINFO_POSTALCODE


### -field RIL_PARAM_OSGEOLOCATIONINFO_COUNTRYCODE


### -field RIL_PARAM_OSGEOLOCATIONINFO_REGIONCODE


### -field RIL_PARAM_OSGEOLOCATIONINFO_FORMATTEDADDRESS


### -field RIL_PARAM_OSGEOLOCATIONINFO_TIMESTAMP


### -field RIL_PARAM_OSGEOLOCATIONINFO_ALL


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>