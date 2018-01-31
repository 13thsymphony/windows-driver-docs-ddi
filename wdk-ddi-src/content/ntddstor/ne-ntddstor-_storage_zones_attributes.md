---
UID : NE:ntddstor._STORAGE_ZONES_ATTRIBUTES
title : "_STORAGE_ZONES_ATTRIBUTES"
author : windows-driver-content
description : Note  This structure is for internal use only and should not be called from your code. .
old-location : storage\storage_zones_attributes.htm
old-project : storage
ms.assetid : 6C86A931-C87C-4273-9409-A45A3FDB8B4C
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : ntddstor/ZonesAttributeTypeAndLengthMayDifferent, ZonesAttributeTypeAndLengthMayDifferent, PSTORAGE_ZONES_ATTRIBUTES enumeration pointer [Storage Devices], *PSTORAGE_ZONES_ATTRIBUTES, PSTORAGE_ZONES_ATTRIBUTES, STORAGE_ZONES_ATTRIBUTES enumeration [Storage Devices], ntddstor/STORAGE_ZONES_ATTRIBUTES, ZonesAttributeTypeSameLengthSame, ntddstor/ZonesAttributeTypeSameLastZoneLengthDifferent, STORAGE_ZONES_ATTRIBUTES, ZonesAttributeTypeMayDifferentLengthSame, ZonesAttributeTypeSameLastZoneLengthDifferent, ntddstor/ZonesAttributeTypeMayDifferentLengthSame, storage.storage_zones_attributes, ntddstor/PSTORAGE_ZONES_ATTRIBUTES, ntddstor/ZonesAttributeTypeSameLengthSame, _STORAGE_ZONES_ATTRIBUTES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : ntddstor.h
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
req.typenames : "*PSTORAGE_ZONES_ATTRIBUTES, STORAGE_ZONES_ATTRIBUTES"
---

# _STORAGE_ZONES_ATTRIBUTES Enumeration
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>

## Syntax
````
typedef enum _STORAGE_ZONES_ATTRIBUTES { 
  ZonesAttributeTypeAndLengthMayDifferent        = 0,
  ZonesAttributeTypeSameLengthSame               = 1,
  ZonesAttributeTypeSameLastZoneLengthDifferent  = 2,
  ZonesAttributeTypeMayDifferentLengthSame       = 3
} STORAGE_ZONES_ATTRIBUTES, *PSTORAGE_ZONES_ATTRIBUTES;
````

## Constants

<table>

<tr>
<td>ZonesAttributeTypeAndLengthMayDifferent</td>
<td>N/A</td>
</tr>

<tr>
<td>ZonesAttributeTypeMayDifferentLengthSame</td>
<td>N/A</td>
</tr>

<tr>
<td>ZonesAttributeTypeSameLastZoneLengthDifferent</td>
<td>N/A</td>
</tr>

<tr>
<td>ZonesAttributeTypeSameLengthSame</td>
<td>N/A</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ntddstor.h |