---
UID : NS:dot11wdi._WDI_MAC_ADDRESS
title : _WDI_MAC_ADDRESS
author : windows-driver-content
description : The WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address.
old-location : netvista\wdi_mac_address.htm
old-project : netvista
ms.assetid : e170b797-f8bb-4d3c-a3ee-5fd1a817a500
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : netvista.wdi_mac_address, WDI_MAC_ADDRESS, PWDI_MAC_ADDRESS structure pointer [Network Drivers Starting with Windows Vista], netvista.wifi_mac_address, dot11wdi/PWDI_MAC_ADDRESS, *PWDI_MAC_ADDRESS, WDI_MAC_ADDRESS structure [Network Drivers Starting with Windows Vista], _WDI_MAC_ADDRESS, dot11wdi/WDI_MAC_ADDRESS, PWDI_MAC_ADDRESS
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
req.typenames : "*PWDI_MAC_ADDRESS, WDI_MAC_ADDRESS"
---

# _WDI_MAC_ADDRESS structure
The 
  WDI_MAC_ADDRESS structure defines an IEEE media access control (MAC) address.

## Syntax
````
typedef struct _WDI_MAC_ADDRESS {
  UINT8 Address[6];
} WDI_MAC_ADDRESS, *PWDI_MAC_ADDRESS;
````

## Members


`Address`

A Wi-Fi MAC address.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dot11wdi.h |