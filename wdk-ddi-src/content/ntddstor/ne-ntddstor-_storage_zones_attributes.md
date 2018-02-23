---
UID: NE:ntddstor._STORAGE_ZONES_ATTRIBUTES
title: "_STORAGE_ZONES_ATTRIBUTES"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zones_attributes.htm
old-project: storage
ms.assetid: 6C86A931-C87C-4273-9409-A45A3FDB8B4C
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: STORAGE_ZONES_ATTRIBUTES, ntddstor/ZonesAttributeTypeMayDifferentLengthSame, ntddstor/STORAGE_ZONES_ATTRIBUTES, ZonesAttributeTypeMayDifferentLengthSame, ZonesAttributeTypeAndLengthMayDifferent, PSTORAGE_ZONES_ATTRIBUTES, PSTORAGE_ZONES_ATTRIBUTES enumeration pointer [Storage Devices], ntddstor/ZonesAttributeTypeAndLengthMayDifferent, ZonesAttributeTypeSameLengthSame, _STORAGE_ZONES_ATTRIBUTES, ZonesAttributeTypeSameLastZoneLengthDifferent, *PSTORAGE_ZONES_ATTRIBUTES, ntddstor/ZonesAttributeTypeSameLastZoneLengthDifferent, STORAGE_ZONES_ATTRIBUTES enumeration [Storage Devices], ntddstor/PSTORAGE_ZONES_ATTRIBUTES, storage.storage_zones_attributes, ntddstor/ZonesAttributeTypeSameLengthSame
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddstor.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddstor.h
apiname:
-	STORAGE_ZONES_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PSTORAGE_ZONES_ATTRIBUTES, STORAGE_ZONES_ATTRIBUTES"
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
| **Header** | ntddstor.h |