---
UID : NS:rilapitypes.RILMSGDCS
title : RILMSGDCS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmsgdcs_2.htm
old-project : netvista
ms.assetid : 50ef03af-3890-40dd-b0ed-7cf048f8530d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILMSGDCS, rilapitypes/RILMSGDCS, netvista.rilmsgdcs_2, RILMSGDCS, RILMSGDCS structure [Network Drivers Starting with Windows Vista]"
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
req.typenames : "*LPRILMSGDCS, RILMSGDCS"
req.product : Windows 10 or later.
---

# RILMSGDCS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMSGDCS {
  DWORD                cbSize;
  DWORD                dwParams;
  RILMSGDCSTYPE        dwType;
  DWORD                dwFlags;
  RILMSGDCSMSGCLASS    dwMsgClass;
  RILMSGDCSALPHABET    dwAlphabet;
  RILMSGDCSINDICATION  dwIndication;
  DWORD                dwLanguage;
} RILMSGDCS, RILMSGDCS;
````

## Members


`cbSize`



`dwAlphabet`



`dwFlags`



`dwIndication`



`dwLanguage`



`dwMsgClass`



`dwParams`



`dwType`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |