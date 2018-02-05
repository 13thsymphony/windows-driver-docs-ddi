---
UID : NS:ntddrilapitypes.RILCBCDMACONFIGINFO
title : RILCBCDMACONFIGINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcbcdmaconfiginfo.htm
old-project : netvista
ms.assetid : 6f8b19ee-a079-4408-8567-39ad832879f2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILCBCDMACONFIGINFO, netvista.rilcbcdmaconfiginfo, *LPRILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILCBCDMACONFIGINFO
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
req.typenames : "*LPRILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO"
---

# RILCBCDMACONFIGINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCBCDMACONFIGINFO {
  BOOL   fAccept;
  DWORD  dwBroadcastMsgLang;
  DWORD  dwBroadcastServiceCategory;
} RILCBCDMACONFIGINFO, RILCBCDMACONFIGINFO;
````

## Members


`dwBroadcastMsgLang`



`dwBroadcastServiceCategory`



`fAccept`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |