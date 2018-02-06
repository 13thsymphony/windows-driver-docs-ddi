---
UID: NE:rilapitypes.RILGEOLOCATIONTYPEMASK
title: RILGEOLOCATIONTYPEMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgeolocationtypemask_2.htm
old-project: netvista
ms.assetid: ffbd2c6d-537a-44f7-a071-21c073d96264
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILGEOLOCATIONTYPEMASK enumeration [Network Drivers Starting with Windows Vista], RIL_GEOLOCATION_LATLONG, rilapitypes/RIL_GEOLOCATION_ALL, RILGEOLOCATIONTYPEMASK, rilapitypes/RIL_GEOLOCATION_CIVIC, netvista.rilgeolocationtypemask_2, rilapitypes/RILGEOLOCATIONTYPEMASK, RIL_GEOLOCATION_CIVIC, rilapitypes/RIL_GEOLOCATION_LATLONG, RIL_GEOLOCATION_ALL
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILGEOLOCATIONTYPEMASK
product: Windows
targetos: Windows
req.typenames: RILGEOLOCATIONTYPEMASK
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |