---
UID : NS:rilapitypes.RILOSGEOLOCATIONINFO
title : RILOSGEOLOCATIONINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilosgeolocationinfo_2.htm
old-project : netvista
ms.assetid : 5207e880-67cb-4cd5-9884-a01e6dd20201
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILOSGEOLOCATIONINFO structure [Network Drivers Starting with Windows Vista], *LPRILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO, netvista.rilosgeolocationinfo_2, rilapitypes/RILOSGEOLOCATIONINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : rilapitypes.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*LPRILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO"
req.product : Windows 10 or later.
---

# RILOSGEOLOCATIONINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILOSGEOLOCATIONINFO {
  DWORD                              cbSize;
  DWORD                              dwParams;
  DWORD                              dwLatitude;
  DWORD                              dwLongitude;
  DWORD                              dwAltitude;
  DWORD                              dwAccuracy;
  RILGEOLOCATIONTYPEMASK             dwLocationInformationMask;
  RILSYSTEMTIME                      stTimeStamp;
  WCHAR [MAXLENGTH_ADDRESS1]         wszAddressLine1;
  WCHAR [MAXLENGTH_ADDRESS2]         wszAddressLine2;
  WCHAR [MAXLENGTH_CITY]             wszCity;
  WCHAR [MAXLENGTH_STATE]            wszState;
  WCHAR [MAXLENGTH_COUNTRY]          wszCountry;
  WCHAR [MAXLENGTH_ZIP]              wszPostalCode;
  WCHAR [MAXLENGTH_FORMATTEDADDRESS] wszFormattedAddress;
  WCHAR [MAXLENGTH_COUNTRYCODE]      wszCountryCode;
  WCHAR [MAXLENGTH_REGIONCODE]       wszRegionCode;
} RILOSGEOLOCATIONINFO, RILOSGEOLOCATIONINFO;
````

## Members


`cbSize`



`dwAccuracy`



`dwAltitude`



`dwLatitude`



`dwLocationInformationMask`



`dwLongitude`



`dwParams`



`stTimeStamp`



`wszAddressLine1`



`wszAddressLine2`



`wszCity`



`wszCountry`



`wszCountryCode`



`wszFormattedAddress`



`wszPostalCode`



`wszRegionCode`



`wszState`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |