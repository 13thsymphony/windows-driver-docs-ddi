---
UID: NS:ntddstor._STORAGE_BUS_RESET_REQUEST
title: "_STORAGE_BUS_RESET_REQUEST"
author: windows-driver-content
description: The STORAGE_BUS_RESET_REQUEST structure is used in conjunction with the IOCTL_STORAGE_RESET_BUS request to specify the path of the bus to be reset.
old-location: storage\storage_bus_reset_request.htm
old-project: storage
ms.assetid: d2f2d2cc-e96b-475c-96eb-d58244a05788
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSTORAGE_BUS_RESET_REQUEST, PSTORAGE_BUS_RESET_REQUEST, PSTORAGE_BUS_RESET_REQUEST structure pointer [Storage Devices], STORAGE_BUS_RESET_REQUEST, STORAGE_BUS_RESET_REQUEST structure [Storage Devices], _STORAGE_BUS_RESET_REQUEST, ntddstor/PSTORAGE_BUS_RESET_REQUEST, ntddstor/STORAGE_BUS_RESET_REQUEST, storage.storage_bus_reset_request, structs-general_ffea4f36-cf98-4961-be14-d8a4cde94fad.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: Ntddstor.h
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
-	ntddstor.h
api_name:
-	STORAGE_BUS_RESET_REQUEST
product: Windows
targetos: Windows
req.typenames: STORAGE_BUS_RESET_REQUEST, *PSTORAGE_BUS_RESET_REQUEST
---

# _STORAGE_BUS_RESET_REQUEST structure
The STORAGE_BUS_RESET_REQUEST structure is used in conjunction with the <a href="..\ntddstor\ni-ntddstor-ioctl_storage_reset_bus.md">IOCTL_STORAGE_RESET_BUS</a> request to specify the path of the bus to be reset.

## Syntax
````
typedef struct _STORAGE_BUS_RESET_REQUEST {
  UCHAR PathId;
} STORAGE_BUS_RESET_REQUEST, *PSTORAGE_BUS_RESET_REQUEST;
````

## Members


`PathId`

Indicates the number of the bus to be reset.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="..\ntddstor\ni-ntddstor-ioctl_storage_reset_bus.md">IOCTL_STORAGE_RESET_BUS</a>