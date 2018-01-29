---
UID : NS:rilapitypes.RILUNSOLICITEDSSINFO_V1
title : RILUNSOLICITEDSSINFO_V1
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilunsolicitedssinfo_v1_2.htm
old-project : netvista
ms.assetid : 37bd1dcd-3cf1-46af-847d-200d0c04167d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILUNSOLICITEDSSINFO_V1 structure [Network Drivers Starting with Windows Vista], rilapitypes/RILUNSOLICITEDSSINFO_V1, *LPRILUNSOLICITEDSSINFO_V1, netvista.rilunsolicitedssinfo_v1_2, RILUNSOLICITEDSSINFO_V1
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
req.typenames : RILUNSOLICITEDSSINFO_V1, *LPRILUNSOLICITEDSSINFO_V1
req.product : Windows 10 or later.
---

# RILUNSOLICITEDSSINFO_V1 structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILUNSOLICITEDSSINFO_V1 {
  DWORD                                 cbSize;
  DWORD                                 dwParams;
  DWORD                                 dwExecutor;
  DWORD                                 dwID;
  RILUNSOLICITEDSSINFONOTIFICATIONCODE  dwNotificationCode;
  RILADDRESS                            raAddress;
  RILSUBADDRESS                         rsaSubAddress;
  DWORD                                 dwCUGIndex;
} RILUNSOLICITEDSSINFO_V1, RILUNSOLICITEDSSINFO_V1;
````

## Members


`cbSize`



`dwCUGIndex`



`dwExecutor`



`dwID`



`dwNotificationCode`



`dwParams`



`raAddress`



`rsaSubAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |