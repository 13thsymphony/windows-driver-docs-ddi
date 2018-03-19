---
UID: NS:ks.KSPIN_PHYSICALCONNECTION
title: KSPIN_PHYSICALCONNECTION
author: windows-driver-content
description: A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a KSPROPERTY_PIN_PHYSICALCONNECTION request.
old-location: stream\kspin_physicalconnection.htm
old-project: stream
ms.assetid: e11c6e8d-a338-4427-af04-bdb07b9e9a73
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: "*PKSPIN_PHYSICALCONNECTION, KSPIN_PHYSICALCONNECTION, KSPIN_PHYSICALCONNECTION structure [Streaming Media Devices], PKSPIN_PHYSICALCONNECTION, PKSPIN_PHYSICALCONNECTION structure pointer [Streaming Media Devices], ks-struct_7b9a3e0f-2cd9-4822-8e8a-03355dc522ed.xml, ks/KSPIN_PHYSICALCONNECTION, ks/PKSPIN_PHYSICALCONNECTION, stream.kspin_physicalconnection"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ks.h
api_name:
-	KSPIN_PHYSICALCONNECTION
product: Windows
targetos: Windows
req.typenames: KSPIN_PHYSICALCONNECTION, *PKSPIN_PHYSICALCONNECTION
---

# KSPIN_PHYSICALCONNECTION structure
A structure of type KSPIN_PHYSICALCONNECTION is returned in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a> request.

## Syntax
````
typedef struct {
  ULONG Size;
  ULONG Pin;
  WCHAR SymbolicLinkName[1];
} KSPIN_PHYSICALCONNECTION, *PKSPIN_PHYSICALCONNECTION;
````

## Members


`Size`

Specifies the size of the structure. Note that the structure contains a dynamic array.

`Pin`

Specifies the PinId of the connected pin on the other filter. (Pin 2 of Wave is connected to Pin 1 of Topology.)

`SymbolicLinkName`

Specifies a string containing the symbolic link name of the connected filter

## Remarks
This structure is used with port class only.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ks.h (include Ks.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565205">KSPROPERTY_PIN_PHYSICALCONNECTION</a>