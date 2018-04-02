---
UID: NS:wdm._IMAGE_POLICY_ENTRY
title: "_IMAGE_POLICY_ENTRY"
author: windows-driver-content
description: This structure is not supported.
old-location: kernel\_image_policy_entry.htm
old-project: kernel
ms.assetid: ea400bef-5c69-4f75-b96e-aae12292fd5a
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IMAGE_POLICY_ENTRY, IMAGE_POLICY_ENTRY structure [Kernel-Mode Driver Architecture], _IMAGE_POLICY_ENTRY, kernel._image_policy_entry, wdm/IMAGE_POLICY_ENTRY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	IMAGE_POLICY_ENTRY
product:
- Windows
targetos: Windows
req.typenames: IMAGE_POLICY_ENTRY
req.product: Windows 10 or later.
---

# _IMAGE_POLICY_ENTRY structure
This structure is not supported.

## Syntax
```
typedef struct _IMAGE_POLICY_ENTRY {
  IMAGE_POLICY_ENTRY_TYPE Type;
  IMAGE_POLICY_ID         PolicyId;
  union {
    PCSTR      AnsiStringValue;
    BOOLEAN    BoolValue;
    INT16      Int16Value;
    INT32      Int32Value;
    INT64      Int64Value;
    INT8       Int8Value;
    const VOID *None;
    UINT16     UInt16Value;
    UINT32     UInt32Value;
    UINT64     UInt64Value;
    UINT8      UInt8Value;
    PCWSTR     UnicodeStringValue;
  } u;
} IMAGE_POLICY_ENTRY;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h |