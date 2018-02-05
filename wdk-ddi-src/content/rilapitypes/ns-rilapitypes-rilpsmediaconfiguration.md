---
UID : NS:rilapitypes.RILPSMEDIACONFIGURATION
title : RILPSMEDIACONFIGURATION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilpsmediaconfiguration_2.htm
old-project : netvista
ms.assetid : eb4500cb-de96-4fbe-971c-d7badc6993af
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilpsmediaconfiguration_2, RILPSMEDIACONFIGURATION, *LPRILPSMEDIACONFIGURATION, rilapitypes/RILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION structure [Network Drivers Starting with Windows Vista]
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
req.typenames : RILPSMEDIACONFIGURATION, *LPRILPSMEDIACONFIGURATION
req.product : Windows 10 or later.
---

# RILPSMEDIACONFIGURATION structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPSMEDIACONFIGURATION {
  RILPSMEDIAPREFERENCE  dwMediaPreference;
  DWORD                 dwServiceType;
} RILPSMEDIACONFIGURATION, RILPSMEDIACONFIGURATION;
````

## Members


`dwMediaPreference`



`dwServiceType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |