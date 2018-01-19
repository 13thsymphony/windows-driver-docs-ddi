---
UID : NS:wditypes._WDI_TYPE_NONCE
title : _WDI_TYPE_NONCE
author : windows-driver-content
description : The WDI_TYPE_NONCE structure defines the SNonce or ANonce (802.11r).
old-location : netvista\wdi_type_nonce.htm
old-project : netvista
ms.assetid : 62E3A714-BA18-4DD5-ACFC-A9EFA37EABB4
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : _WDI_TYPE_NONCE, WDI_TYPE_NONCE, *PWDI_TYPE_NONCE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : wditypes.hpp
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : WDI_TYPE_NONCE
req.alt-loc : wditypes.hpp
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
req.typenames : WDI_TYPE_NONCE, *PWDI_TYPE_NONCE
req.product : Windows 10 or later.
---

# _WDI_TYPE_NONCE structure
The WDI_TYPE_NONCE structure defines the SNonce or ANonce (802.11r).

## Syntax
````
typedef struct _WDI_TYPE_NONCE {
  UINT8 Nonce[32];
} WDI_TYPE_NONCE, *PWDI_TYPE_NONCE;
````

## Members

        
            `Nonce`

            The SNonce or ANonce.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wditypes.hpp |