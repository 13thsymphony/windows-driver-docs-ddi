---
UID: NS:hidpddi._HIDP_GETCOLDESC_DBG
title: "_HIDP_GETCOLDESC_DBG"
author: windows-driver-content
description: Contains the error code indicating the failure in parsing the report descriptor. This structure is used in the HidP_GetCollectionDescription call.
old-location: hid\hidp_getcoldesc_dbg.htm
old-project: hid
ms.assetid: 65EEEDED-14FE-4275-9314-276E544427DE
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PHIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG, HIDP_GETCOLDESC_DBG structure [Human Input Devices], PHIDP_GETCOLDESC_DBG, PHIDP_GETCOLDESC_DBG structure pointer [Human Input Devices], _HIDP_GETCOLDESC_DBG, hid.hidp_getcoldesc_dbg, hidpddi/HIDP_GETCOLDESC_DBG, hidpddi/PHIDP_GETCOLDESC_DBG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hidpddi.h
req.include-header: Hidpddi.h
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hidpddi.h
api_name:
-	HIDP_GETCOLDESC_DBG
product:
- Windows
targetos: Windows
req.typenames: HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG
---

# _HIDP_GETCOLDESC_DBG structure
Contains the error code indicating the failure in parsing the report 
                                      descriptor. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a> call.

## Syntax
```
typedef struct _HIDP_GETCOLDESC_DBG {
  ULONG BreakOffset;
  ULONG ErrorCode;
  ULONG Args[6];
} HIDP_GETCOLDESC_DBG, *PHIDP_GETCOLDESC_DBG;
```

## Members


`BreakOffset`

The byte offset in the report descriptor where the parsing error occurred.

`ErrorCode`

Indicates the parsing error, if it’s not HIDP_GETCOLDESC_SUCCESS.

All possible values are defined in hidpddi.h, from HIDP_GETCOLDESC_SUCCESS to the end  of the file.

`Args`

Error-specific arguments. These are described as comments in the possible values for <b>ErrorCode</b> in hidpddi.h.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | hidpddi.h (include Hidpddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt740164">HidP_GetCollectionDescription</a>