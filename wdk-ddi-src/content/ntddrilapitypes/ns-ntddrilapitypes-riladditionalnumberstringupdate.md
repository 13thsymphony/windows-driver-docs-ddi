---
UID : NS:ntddrilapitypes.RILADDITIONALNUMBERSTRINGUPDATE
title : RILADDITIONALNUMBERSTRINGUPDATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riladditionalnumberstringupdate.htm
old-project : netvista
ms.assetid : 43fe1e25-be15-4f7a-8ecf-e4492235c6c2
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE structure [Network Drivers Starting with Windows Vista], netvista.riladditionalnumberstringupdate, *LPRILADDITIONALNUMBERSTRINGUPDATE, ntddrilapitypes/RILADDITIONALNUMBERSTRINGUPDATE
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
req.typenames : "*LPRILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE"
---

# RILADDITIONALNUMBERSTRINGUPDATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILADDITIONALNUMBERSTRINGUPDATE {
  DWORD                     cbSize;
  HUICCAPP                  hUiccApp;
  RILPHONEBOOKANSOPERATION  dwOpType;
  DWORD                     dwNumId;
  WCHAR [256]               wszText;
} RILADDITIONALNUMBERSTRINGUPDATE, RILADDITIONALNUMBERSTRINGUPDATE;
````

## Members


`cbSize`



`dwNumId`



`dwOpType`



`hUiccApp`



`wszText`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |