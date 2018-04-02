---
UID: NS:ntddstor._STORAGE_IDENTIFIER
title: "_STORAGE_IDENTIFIER"
author: windows-driver-content
description: The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.
old-location: storage\storage_identifier.htm
old-project: storage
ms.assetid: f2b0610a-dffa-48fb-bc5a-355fa9f05770
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER, PSTORAGE_IDENTIFIER structure pointer [Storage Devices], STORAGE_IDENTIFIER, STORAGE_IDENTIFIER structure [Storage Devices], _STORAGE_IDENTIFIER, ntddstor/PSTORAGE_IDENTIFIER, ntddstor/STORAGE_IDENTIFIER, storage.storage_identifier, structs-general_29c666d7-3e61-44fe-a36e-979418dbb958.xml"
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
-	STORAGE_IDENTIFIER
product: Windows
targetos: Windows
req.typenames: STORAGE_IDENTIFIER, *PSTORAGE_IDENTIFIER
---

# _STORAGE_IDENTIFIER structure
The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.

## Syntax
```
typedef struct _STORAGE_IDENTIFIER {
  __WRAPPED__ STORAGE_IDENTIFIER_CODE_SET CodeSet;
  __WRAPPED__ STORAGE_IDENTIFIER_TYPE     Type;
  __WRAPPED__ USHORT                      IdentifierSize;
  __WRAPPED__ USHORT                      NextOffset;
  __WRAPPED__ STORAGE_ASSOCIATION_TYPE    Association;
  __WRAPPED__ UCHAR                       Identifier[1];
} STORAGE_IDENTIFIER, *PSTORAGE_IDENTIFIER;
```

## Members


`CodeSet`

Specifies the code set used by a SCSI identification descriptor to identify a logical unit.

`Type`

Contains an enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566990">STORAGE_IDENTIFIER_TYPE</a> that indicates the identifier type.

`IdentifierSize`

Specifies the size in bytes of the identifier.

`NextOffset`

Specifies the offset in bytes from the current descriptor to the next descriptor.

`Association`

Contains an enumerator value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff566349">STORAGE_ASSOCIATION_TYPE</a> that indicates whether the descriptor identifies a device or a port.

`Identifier`

Contains the identifier associated with this descriptor.

## Remarks
Every device identification page (page code 0x83) of SCSI vital product data contains a series of identification descriptors. The STORAGE_IDENTIFIER structure represents a SCSI identification descriptor.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h (include Ntddstor.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566349">STORAGE_ASSOCIATION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566990">STORAGE_IDENTIFIER_TYPE</a>