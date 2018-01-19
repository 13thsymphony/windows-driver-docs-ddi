---
UID : NS:ntddrilapitypes.RILCALLCUSTOMMEDIASTATE
title : RILCALLCUSTOMMEDIASTATE
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilcallcustommediastate.htm
old-project : netvista
ms.assetid : 8975871a-9977-4dcb-82d8-0c16c1861a42
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILCALLCUSTOMMEDIASTATE, *LPRILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE
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
req.alt-api : RILCALLCUSTOMMEDIASTATE
req.alt-loc : ntddrilapitypes.h
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
req.typenames : "*LPRILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE"
---

# RILCALLCUSTOMMEDIASTATE structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILCALLCUSTOMMEDIASTATE {
  DWORD [1] dwCustomStateSpecific;
} RILCALLCUSTOMMEDIASTATE, RILCALLCUSTOMMEDIASTATE;
````

## Members

        
            `dwCustomStateSpecific`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |