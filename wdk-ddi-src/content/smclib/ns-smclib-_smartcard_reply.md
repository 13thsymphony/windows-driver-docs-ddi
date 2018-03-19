---
UID: NS:smclib._SMARTCARD_REPLY
title: "_SMARTCARD_REPLY"
author: windows-driver-content
description: Describes the reply buffer received from the smart card.
old-location: smartcrd\smartcard_reply.htm
old-project: smartcrd
ms.assetid: DB41648B-8812-4358-BECE-8029016E5631
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: "*PSMARTCARD_REPLY, PSMARTCARD_REPLY, PSMARTCARD_REPLY structure pointer [Smart Card Reader Devices], SMARTCARD_REPLY, SMARTCARD_REPLY structure [Smart Card Reader Devices], _SMARTCARD_REPLY, smartcrd.smartcard_reply, smclib/PSMARTCARD_REPLY, smclib/SMARTCARD_REPLY"
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
-	SMARTCARD_REPLY
product: Windows
targetos: Windows
req.typenames: SMARTCARD_REPLY, *PSMARTCARD_REPLY
req.product: Windows 10 or later.
---

# _SMARTCARD_REPLY structure
Describes the reply buffer received from the smart card.

## Syntax
````
typedef struct _SMARTCARD_REPLY {
  PUCHAR 	Buffer;
  ULONG  BufferSize;
  ULONG  BufferLength;
} SMARTCARD_REPLY, *PSMARTCARD_REPLY;
````

## Members


`Buffer`

Pointer to a buffer that  receives smart card data.

`BufferSize`

Size of the buffer pointed to by <i>Buffer</i>.

`BufferLength`

Number of bytes received from the card.

## Remarks
The client driver must receive data in this buffer and   adjust <i>BufferLength</i> to the number of received bytes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | smclib.h (include Smclib.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946592">SmcCxGetSmartcardReplyBuffer</a>