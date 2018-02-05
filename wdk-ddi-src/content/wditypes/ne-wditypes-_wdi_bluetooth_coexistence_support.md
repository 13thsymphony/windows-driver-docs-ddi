---
UID : NE:wditypes._WDI_BLUETOOTH_COEXISTENCE_SUPPORT
title : "_WDI_BLUETOOTH_COEXISTENCE_SUPPORT"
author : windows-driver-content
description : The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values.
old-location : netvista\wdi_bluetooth_coexistence_support.htm
old-project : netvista
ms.assetid : 88642615-D5DD-4C0E-BAAA-308EB6050E77
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : wditypes/WDI_BLUETOOTH_COEXISTENCE_SUPPORT, netvista.wdi_bluetooth_coexistence_support, WDI_BLUETOOTH_COEXISTENCE_SUPPORT, wditypes/WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE, wditypes/WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1, _WDI_BLUETOOTH_COEXISTENCE_SUPPORT, WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED, wditypes/WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED, WDI_BLUETOOTH_COEXISTENCE_UNKNOWN, wditypes/WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED, WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1, WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration [Network Drivers Starting with Windows Vista], WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE, wditypes/WDI_BLUETOOTH_COEXISTENCE_UNKNOWN, WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : wditypes.hpp
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_BLUETOOTH_COEXISTENCE_SUPPORT
req.product : Windows 10 or later.
---

# _WDI_BLUETOOTH_COEXISTENCE_SUPPORT Enumeration
The WDI_BLUETOOTH_COEXISTENCE_SUPPORT enumeration defines Bluetooth coexistence support values.

## Syntax
````
typedef enum _WDI_BLUETOOTH_COEXISTENCE_SUPPORT { 
  WDI_BLUETOOTH_COEXISTENCE_UNKNOWN                   = 0,
  WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED    = 1,
  WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1      = 2,
  WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED  = 3,
  WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE        = 4
} WDI_BLUETOOTH_COEXISTENCE_SUPPORT;
````

## Constants

<table>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_MAX</td>
<td></td>
</tr>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_MUTUALLY_EXCLUSIVE</td>
<td>Wi-Fi and Bluetooth are mutually exclusive. One of the two stops working.</td>
</tr>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_PERFORMANCE_MAINTAINED</td>
<td>Wi-Fi and Bluetooth work at the same performance level during coexistence.</td>
</tr>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_UNKNOWN</td>
<td>Unknown.</td>
</tr>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_WIFI_DEGRADED_TO_1x1</td>
<td>Wi-Fi centered. On a 2X2 device, Wi-Fi and Bluetooth coexists. Wi-Fi performance is reduced to 1X1 level.</td>
</tr>

<tr>
<td>WDI_BLUETOOTH_COEXISTENCE_WIFI_THROUGHPUT_DEGRADED</td>
<td>Bluetooth centered. When coexisting, Bluetooth has priority and restricts Wi-Fi performance.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | wditypes.hpp |