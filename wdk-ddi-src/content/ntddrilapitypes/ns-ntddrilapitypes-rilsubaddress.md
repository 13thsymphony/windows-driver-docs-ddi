---
UID : NS:ntddrilapitypes.RILSUBADDRESS
title : RILSUBADDRESS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilsubaddress.htm
old-project : netvista
ms.assetid : 0a1f9e89-df17-4802-9685-06a2eedbc0e5
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*LPRILSUBADDRESS, RILSUBADDRESS structure [Network Drivers Starting with Windows Vista], ntddrilapitypes/RILSUBADDRESS, RILSUBADDRESS, netvista.rilsubaddress"
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
req.typenames : RILSUBADDRESS, *LPRILSUBADDRESS
---

# RILSUBADDRESS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILSUBADDRESS {
  DWORD              cbSize;
  DWORD              dwParams;
  RILSUBADDRESSTYPE  dwType;
  WCHAR [256]        wszSubAddress;
} RILSUBADDRESS, RILSUBADDRESS;
````

## Members


`cbSize`



`dwParams`



`dwType`



`wszSubAddress`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |