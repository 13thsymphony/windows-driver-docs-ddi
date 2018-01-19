---
UID : NC:drmk.PFNDRMDESTROYCONTENT
title : PFNDRMDESTROYCONTENT
author : windows-driver-content
description : This callback function is reserved for system use.
old-location : audio\pfndrmdestroycontent.htm
old-project : audio
ms.assetid : 24B98C91-9EB3-4D00-8D58-F6C96610946A
ms.author : windowsdriverdev
ms.date : 12/14/2017
ms.keywords : _WDI_TX_METADATA, WDI_TX_METADATA, *PWDI_TX_METADATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : drmk.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DRMDestroyContent
req.alt-loc : Drmk.h
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
req.typenames : WDI_TX_METADATA, *PWDI_TX_METADATA
---


# PFNDRMDESTROYCONTENT callback function
This callback function is reserved for system use.

## Syntax

```
PFNDRMDESTROYCONTENT Pfndrmdestroycontent;

NTSTATUS Pfndrmdestroycontent(
  ULONG ContentId
)
{...}
```

## Parameters

`ContentId`

This parameter is reserved for system use.


## Return Value

This return value is reserved for system use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | drmk.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |