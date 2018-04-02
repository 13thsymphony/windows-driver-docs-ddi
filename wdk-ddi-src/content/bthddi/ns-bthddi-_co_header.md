---
UID: NS:bthddi._CO_HEADER
title: "_CO_HEADER"
author: windows-driver-content
description: The CO_HEADER structure is used to specify values for the Header member of the L2CAP_CONFIG_OPTION structure.
old-location: bltooth\co_header.htm
old-project: bltooth
ms.assetid: 76fa3316-bbec-4bf1-8cb8-d92e9f54d2d6
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: CO_HEADER, CO_HEADER structure [Bluetooth Devices], _CO_HEADER, bltooth.co_header, bth_structs_bb345dd7-5895-472a-ab07-38c8b5ac6a72.xml, bthddi/CO_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	CO_HEADER
product:
- Windows
targetos: Windows
req.typenames: CO_HEADER
---

# _CO_HEADER structure
The CO_HEADER structure is used to specify values for the 
  <b>Header</b> member of the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff536757">L2CAP_CONFIG_OPTION</a> structure.

## Syntax
```
typedef struct _CO_HEADER {
  CO_TYPE   Type;
  CO_LENGTH Length;
} CO_HEADER;
```

## Members


`Type`

The type of the vendor-specific option stored in the L2CAP_CONFIG_OPTION structure. This can
     accept either an option or a hint.

`Length`

The size, in bytes, of the vendor-specific option stored in the L2CAP_CONFIG_OPTION
     structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Versions:\_Supported in Windows Vista, and later. Versions:\_Supported in Windows Vista, and later. |
| **Header** | bthddi.h (include Bthddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff536757">L2CAP_CONFIG_OPTION</a>