---
UID : NS:ntddrilapitypes.RILGEOLOCATIONREQUESTINFO
title : RILGEOLOCATIONREQUESTINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgeolocationrequestinfo.htm
old-project : netvista
ms.assetid : f3fa5212-66c1-45f8-a96f-78d1f2f01fe8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilgeolocationrequestinfo, RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO structure [Network Drivers Starting with Windows Vista], *LPRILGEOLOCATIONREQUESTINFO, ntddrilapitypes/RILGEOLOCATIONREQUESTINFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ntddrilapitypes.h
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
req.typenames : "*LPRILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO"
---

# RILGEOLOCATIONREQUESTINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGEOLOCATIONREQUESTINFO {
  DWORD  cbSize;
  DWORD  dwLatitude;
  DWORD  dwLongitude;
  DWORD  dwAltitude;
} RILGEOLOCATIONREQUESTINFO, RILGEOLOCATIONREQUESTINFO;
````

## Members


`cbSize`



`dwAltitude`



`dwLatitude`



`dwLongitude`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |