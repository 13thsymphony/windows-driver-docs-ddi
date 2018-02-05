---
UID : NS:ntddrilapitypes.RILPHONEBOOKLOCATION
title : RILPHONEBOOKLOCATION
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilphonebooklocation.htm
old-project : netvista
ms.assetid : a4d47312-87e2-4147-94f6-ff9c9d452211
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILPHONEBOOKLOCATION, netvista.rilphonebooklocation, RILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION structure [Network Drivers Starting with Windows Vista], *LPRILPHONEBOOKLOCATION
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
req.typenames : "*LPRILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION"
---

# RILPHONEBOOKLOCATION structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPHONEBOOKLOCATION {
  DWORD                       cbSize;
  HUICCAPP                    hUiccApp;
  RILPHONEENTRYSTORELOCATION  dwStoreLocation;
  DWORD                       dwIndex;
} RILPHONEBOOKLOCATION, RILPHONEBOOKLOCATION;
````

## Members


`cbSize`



`dwIndex`



`dwStoreLocation`



`hUiccApp`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |