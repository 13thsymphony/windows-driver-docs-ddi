---
UID : NS:ntddrilapitypes.RILGETRADIOSTATEDETAILSPARAMS
title : RILGETRADIOSTATEDETAILSPARAMS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilgetradiostatedetailsparams.htm
old-project : netvista
ms.assetid : faee1991-a183-4285-af14-402094dc6694
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILGETRADIOSTATEDETAILSPARAMS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILGETRADIOSTATEDETAILSPARAMS, netvista.rilgetradiostatedetailsparams, RILGETRADIOSTATEDETAILSPARAMS, *LPRILGETRADIOSTATEDETAILSPARAMS
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
req.typenames : "*LPRILGETRADIOSTATEDETAILSPARAMS, RILGETRADIOSTATEDETAILSPARAMS"
---

# RILGETRADIOSTATEDETAILSPARAMS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILGETRADIOSTATEDETAILSPARAMS {
  DWORD  dwGroupId;
  DWORD  dwItemId;
} RILGETRADIOSTATEDETAILSPARAMS, RILGETRADIOSTATEDETAILSPARAMS;
````

## Members


`dwGroupId`



`dwItemId`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |