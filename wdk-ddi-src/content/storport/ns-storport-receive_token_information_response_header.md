---
UID: NS:storport.RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
title: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
author: windows-driver-content
description: A token, created as a representation of data (ROD), for an offload read data operation is returned in a RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure.
old-location: storage\receive_token_information_response_header.htm
old-project: storage
ms.assetid: 54168476-1C55-4343-858C-7FBA863D35D0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure pointer [Storage Devices], RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure [Storage Devices], scsi/PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, scsi/RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, storage.receive_token_information_response_header"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Scsi.h, Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8.
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
-	scsi.h
api_name:
-	RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
product: Windows
targetos: Windows
req.typenames: RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER, *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER
req.product: Windows 10 or later.
---

# RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER structure
A token, created as a representation of data (ROD), for an offload read data operation is returned in a <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure.

## Syntax
```
typedef struct RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER {
  UCHAR TokenDescriptorsLength[4];
  UCHAR TokenDescriptor[ANYSIZE_ARRAY];
}  *PRECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER;
```

## Members


`TokenDescriptorsLength`

The length, in bytes, of the <b>TokenDescriptor</b> member.

`TokenDescriptor`

The data containing a token created as the offload read ROD.

## Remarks
The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure is included with a <a href="https://msdn.microsoft.com/library/windows/hardware/hh967731">RECEIVE_TOKEN_INFORMATION_HEADER</a>structure  as a response to a POPULATE TOKEN command. The <b>RECEIVE_TOKEN_INFORMATION_RESPONSE_HEADER</b> structure follows the <b>SenseData</b> member of <b>RECEIVE_TOKEN_INFORMATION_HEADER</b>.

All multibyte values are in big endian format. Prior to evaluation, these values must be converted to match the endian format of the current platform.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Header** | storport.h (include Scsi.h, Minitape.h, Storport.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh967730">POPULATE_TOKEN_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh967731">RECEIVE_TOKEN_INFORMATION_HEADER</a>