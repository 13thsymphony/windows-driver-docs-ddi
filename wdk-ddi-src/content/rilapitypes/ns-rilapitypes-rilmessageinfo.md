---
UID : NS:rilapitypes.RILMESSAGEINFO
title : RILMESSAGEINFO
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilmessageinfo_2.htm
old-project : netvista
ms.assetid : db7b8526-e70a-4589-a128-58641c865d58
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : RILMESSAGEINFO structure [Network Drivers Starting with Windows Vista], RILMESSAGEINFO, rilapitypes/RILMESSAGEINFO, netvista.rilmessageinfo_2, *LPRILMESSAGEINFO
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
req.typenames : "*LPRILMESSAGEINFO, RILMESSAGEINFO"
req.product : Windows 10 or later.
---

# RILMESSAGEINFO structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILMESSAGEINFO {
  DWORD             cbSize;
  HUICCAPP          hUiccApp;
  DWORD             dwParams;
  DWORD             dwIndex;
  RILMESSAGESTATUS  dwStatus;
  RILMESSAGE        rmMessage;
} RILMESSAGEINFO, RILMESSAGEINFO;
````

## Members


`cbSize`



`dwIndex`



`dwParams`



`dwStatus`



`hUiccApp`



`rmMessage`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rilapitypes.h |