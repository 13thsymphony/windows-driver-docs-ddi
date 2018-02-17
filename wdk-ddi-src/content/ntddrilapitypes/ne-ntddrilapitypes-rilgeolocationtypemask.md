---
UID: NE:ntddrilapitypes.RILGEOLOCATIONTYPEMASK
title: RILGEOLOCATIONTYPEMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationtypemask.htm
old-project: netvista
ms.assetid: 8d1f6570-adc1-4389-b20b-7c7e05f1c9bf
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_GEOLOCATION_LATLONG, RIL_GEOLOCATION_ALL, ntddrilapitypes/RIL_GEOLOCATION_CIVIC, RIL_GEOLOCATION_CIVIC, ntddrilapitypes/RIL_GEOLOCATION_LATLONG, RILGEOLOCATIONTYPEMASK, netvista.rilgeolocationtypemask, ntddrilapitypes/RIL_GEOLOCATION_ALL, ntddrilapitypes/RILGEOLOCATIONTYPEMASK, RILGEOLOCATIONTYPEMASK enumeration [Network Drivers Starting with Windows Vista]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILGEOLOCATIONTYPEMASK
product: Windows
targetos: Windows
req.typenames: RILGEOLOCATIONTYPEMASK
---

# RILGEOLOCATIONTYPEMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGEOLOCATIONTYPEMASK { 
  RIL_GEOLOCATION_CIVIC,
  RIL_GEOLOCATION_LATLONG,
  RIL_GEOLOCATION_ALL
} RILGEOLOCATIONTYPEMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_GEOLOCATION_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOLOCATION_CIVIC</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOLOCATION_LATLONG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_GEOLOCATION_NONE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |