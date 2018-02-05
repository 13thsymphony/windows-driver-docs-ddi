---
UID : NS:dot11wdi._WDI_TXRX_TARGET_CONFIGURATION
title : "_WDI_TXRX_TARGET_CONFIGURATION"
author : windows-driver-content
description : The WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.
old-location : netvista\wdi_txrx_target_configuration.htm
old-project : netvista
ms.assetid : 5a2d8bdf-cfc2-4724-aab3-0277edb477e7
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : dot11wdi/WDI_TXRX_TARGET_CONFIGURATION, WDI_TXRX_TARGET_CONFIGURATION structure [Network Drivers Starting with Windows Vista], _WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION, PWDI_TXRX_TARGET_CONFIGURATION structure pointer [Network Drivers Starting with Windows Vista], PWDI_TXRX_TARGET_CONFIGURATION, netvista.wifi_txrx_target_configuration, WDI_TXRX_TARGET_CONFIGURATION, dot11wdi/PWDI_TXRX_TARGET_CONFIGURATION, netvista.wdi_txrx_target_configuration
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : dot11wdi.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
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
req.irql : PASSIVE_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION
---

# _WDI_TXRX_TARGET_CONFIGURATION structure
The 
  WDI_TXRX_TARGET_CONFIGURATION structure defines the target configuration.

## Syntax
````
typedef struct _WDI_TXRX_TARGET_CONFIGURATION {
  WDI_TXRX_PARAMETERS TxRxParams;
  UINT8               MaxNumPorts;
  UINT8               MaxNumPeers;
} WDI_TXRX_TARGET_CONFIGURATION, *PWDI_TXRX_TARGET_CONFIGURATION;
````

## Members


`MaxNumPeers`

Specifies the maximum number of peers.

`MaxNumPorts`

Specifies the maximum number of ports.

`TxRxParams`

Specifies the TXRX parameters.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | dot11wdi.h |