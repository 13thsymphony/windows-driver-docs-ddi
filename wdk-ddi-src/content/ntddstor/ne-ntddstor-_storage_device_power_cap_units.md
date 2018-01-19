---
UID : NE:ntddstor._STORAGE_DEVICE_POWER_CAP_UNITS
title : _STORAGE_DEVICE_POWER_CAP_UNITS
author : windows-driver-content
description : The units of the maximum power threshold.
old-location : storage\storage_device_power_cap_units.htm
old-project : storage
ms.assetid : 199900F4-90A7-4F2E-B85E-25BF3593D50B
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : _STORAGE_DEVICE_POWER_CAP_UNITS, STORAGE_DEVICE_POWER_CAP_UNITS, *PSTORAGE_DEVICE_POWER_CAP_UNITS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddstor.h
req.include-header : Ntddstor.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : STORAGE_DEVICE_POWER_CAP_UNITS
req.alt-loc : ntddstor.h
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
req.typenames : STORAGE_DEVICE_POWER_CAP_UNITS, *PSTORAGE_DEVICE_POWER_CAP_UNITS
---

# _STORAGE_DEVICE_POWER_CAP_UNITS Enumeration
The units of the maximum power threshold.

## Syntax
````
typedef enum _STORAGE_DEVICE_POWER_CAP_UNITS { 
  StorageDevicePowerCapUnitsPercent,
  StorageDevicePowerCapUnitsMilliwatts
} STORAGE_DEVICE_POWER_CAP_UNITS;
````

## Constants

<table>

<tr>
<td>StorageDevicePowerCapUnitsMilliwatts</td>
<td>Units in milliwatts.</td>
</tr>

<tr>
<td>StorageDevicePowerCapUnitsPercent</td>
<td>Units in percent.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h (include Ntddstor.h) |