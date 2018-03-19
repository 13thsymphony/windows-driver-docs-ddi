---
UID: NS:smclib._SMARTCARD_REQUEST
title: "_SMARTCARD_REQUEST"
author: windows-driver-content
description: Describes the request buffer that contains data to send to the card.
old-location: smartcrd\smartcard_request.htm
old-project: smartcrd
ms.assetid: B5FF5B24-12E6-424A-B09A-4B0572621088
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PSMARTCARD_REQUEST, PSMARTCARD_REQUEST, PSMARTCARD_REQUEST structure pointer [Smart Card Reader Devices], SMARTCARD_REQUEST, SMARTCARD_REQUEST structure [Smart Card Reader Devices], _SMARTCARD_REQUEST, smartcrd.smartcard_request, smclib/PSMARTCARD_REQUEST, smclib/SMARTCARD_REQUEST"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: smclib.h
req.include-header: Smclib.h
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
req.irql: Any level (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Smclib.h
api_name:
-	SMARTCARD_REQUEST
product: Windows
targetos: Windows
req.typenames: SMARTCARD_REQUEST, *PSMARTCARD_REQUEST
req.product: Windows 10 or later.
---

# _SMARTCARD_REQUEST structure
Describes the request buffer that contains data to send to the card.

## Syntax
````
typedef struct _SMARTCARD_REPLY {
  PUCHAR 	Buffer;
  ULONG  BufferSize;
  ULONG  BufferLength;
} SMARTCARD_REQUEST, *PSMARTCARD_REQUEST;
````

## Members


`Buffer`

Pointer to a buffer that  contains data to send.

`BufferSize`

Size of the buffer pointed to by <i>Buffer</i>.

`BufferLength`

Number of bytes required for this command.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smclib.h (include Smclib.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946593">SmcCxGetSmartcardRequestBuffer</a>