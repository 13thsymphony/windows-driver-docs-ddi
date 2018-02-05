---
UID : NS:rilapitypes.RILPSMEDIACONFIGURATIONSET
title : RILPSMEDIACONFIGURATIONSET
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilpsmediaconfigurationset_2.htm
old-project : netvista
ms.assetid : cdaa161e-2481-497c-8a9b-4c07a3d99d1f
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.rilpsmediaconfigurationset_2, *LPRILPSMEDIACONFIGURATIONSET, rilapitypes/RILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET structure [Network Drivers Starting with Windows Vista], RILPSMEDIACONFIGURATIONSET
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
req.typenames : RILPSMEDIACONFIGURATIONSET, *LPRILPSMEDIACONFIGURATIONSET
req.product : Windows 10 or later.
---

# RILPSMEDIACONFIGURATIONSET structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPSMEDIACONFIGURATIONSET {
  DWORD                       cbSize;
  DWORD                       dwExecutor;
  DWORD                       dwNumMediaConfiguration;
  RILPSMEDIACONFIGURATION [1] stMediaConfiguration;
} RILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET;
````

## Members


`cbSize`



`dwExecutor`



`dwNumMediaConfiguration`



`stMediaConfiguration`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |