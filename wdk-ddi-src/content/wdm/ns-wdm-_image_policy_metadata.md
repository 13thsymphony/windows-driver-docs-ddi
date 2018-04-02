---
UID: NS:wdm._IMAGE_POLICY_METADATA
title: "_IMAGE_POLICY_METADATA"
author: windows-driver-content
description: This structure is not supported.
old-location: kernel\_image_policy_metadata.htm
old-project: kernel
ms.assetid: b7dfb3c8-40d5-4ec0-9710-7c04fb414f32
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: IMAGE_POLICY_METADATA, IMAGE_POLICY_METADATA structure [Kernel-Mode Driver Architecture], _IMAGE_POLICY_METADATA, kernel._image_policy_metadata, wdm/IMAGE_POLICY_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Wdm.h
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
-	IMAGE_POLICY_METADATA
product:
- Windows
targetos: Windows
req.typenames: IMAGE_POLICY_METADATA
req.product: Windows 10 or later.
---

# _IMAGE_POLICY_METADATA structure
This structure is not supported.

## Syntax
```
typedef struct _IMAGE_POLICY_METADATA {
  UCHAR              Version;
  UCHAR              Reserved0[7];
  ULONGLONG          ApplicationId;
  IMAGE_POLICY_ENTRY Policies[];
} IMAGE_POLICY_METADATA;
```

## Members



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wdm.h (include Wdm.h, Wdm.h) |