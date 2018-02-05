---
UID : NS:ntddrilapitypes.RILADDITIONALCALLERINFO
title : RILADDITIONALCALLERINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\riladditionalcallerinfo.htm
old-project : netvista
ms.assetid : dd622ebc-beba-4c96-a0e8-97ad614e3937
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : ntddrilapitypes/RILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO, netvista.riladditionalcallerinfo, *LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO structure [Network Drivers Starting with Windows Vista]
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
req.typenames : "*LPRILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO"
---

# RILADDITIONALCALLERINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILADDITIONALCALLERINFO {
  DWORD     cbSize;
  DWORD     dwParams;
  DWORD     dwExecutor;
  DWORD     dwCallId;
  DWORD     dwCallerInfoLength;
  WCHAR [1] wszCallerInfo;
} RILADDITIONALCALLERINFO, RILADDITIONALCALLERINFO;
````

## Members


`cbSize`



`dwCallerInfoLength`



`dwCallId`



`dwExecutor`



`dwParams`



`wszCallerInfo`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |