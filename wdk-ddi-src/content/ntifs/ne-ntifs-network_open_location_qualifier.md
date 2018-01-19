---
UID : NE:ntifs.NETWORK_OPEN_LOCATION_QUALIFIER
title : NETWORK_OPEN_LOCATION_QUALIFIER
author : windows-driver-content
description : The NETWORK_OPEN_LOCATION_QUALIFIER enumeration type contains values that identify the kind of location restriction to attach to a file.
old-location : ifsk\network_open_location_qualifier.htm
old-project : ifsk
ms.assetid : 7762bf83-82cc-4eef-9699-d093a8c2b986
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : NETWORK_OPEN_LOCATION_QUALIFIER, NETWORK_OPEN_LOCATION_QUALIFIER
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntifs.h
req.include-header : Ntifs.h
req.target-type : Windows
req.target-min-winverclnt : This enumeration type is available starting with Windows Vista.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : NETWORK_OPEN_LOCATION_QUALIFIER
req.alt-loc : ntifs.h
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
req.typenames : NETWORK_OPEN_LOCATION_QUALIFIER
---

# NETWORK_OPEN_LOCATION_QUALIFIER Enumeration
The NETWORK_OPEN_LOCATION_QUALIFIER enumeration type contains values that identify the kind of location restriction to attach to a file.

## Syntax
````
typedef enum  { 
  NetworkOpenLocationAny       = 0,
  NetworkOpenLocationRemote    = 1,
  NetworkOpenLocationLoopback  = 2
} NETWORK_OPEN_LOCATION_QUALIFIER;
````

## Constants

<table>

<tr>
<td>NetworkOpenLocationAny</td>
<td>Indicates that the file has no location restrictions. That is, a caller can open the file whether it resides remotely or locally.</td>
</tr>

<tr>
<td>NetworkOpenLocationLoopback</td>
<td>Indicates that the file is restricted to only opening locally. That is, a caller can only open the file if it resides on the same computer as the caller.</td>
</tr>

<tr>
<td>NetworkOpenLocationRemote</td>
<td>Indicates that the file is restricted to only opening remotely. That is, a caller can only open the file if it resides on a different computer from the computer that the caller resides on.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntifs.h (include Ntifs.h) |