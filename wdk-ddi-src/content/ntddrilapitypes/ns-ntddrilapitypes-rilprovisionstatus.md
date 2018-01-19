---
UID : NS:ntddrilapitypes.RILPROVISIONSTATUS
title : RILPROVISIONSTATUS
author : windows-driver-content
description : This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location : netvista\rilprovisionstatus.htm
old-project : netvista
ms.assetid : 5295f07d-9800-47f0-a827-515fcdad04eb
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : RILPROVISIONSTATUS, RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS
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
req.alt-api : RILPROVISIONSTATUS
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
req.typenames : RILPROVISIONSTATUS, *LPRILPROVISIONSTATUS
---

# RILPROVISIONSTATUS structure
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef struct _RILPROVISIONSTATUS {
  DWORD                              cbSize;
  DWORD                              dwExecutor;
  RILPROVISIONSTATUSPROVISIONSTATUS  dwProvisionStatus;
} RILPROVISIONSTATUS, RILPROVISIONSTATUS;
````

## Members

        
            `cbSize`

            
        
            `dwExecutor`

            
        
            `dwProvisionStatus`

            


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddrilapitypes.h |