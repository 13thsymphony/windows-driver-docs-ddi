---
UID: NS:wiadef._WIA_PATCH_CODE_INFO
title: "_WIA_PATCH_CODE_INFO"
author: windows-driver-content
description: The WIA_PATCH_CODE_INFO structure stores information for one decoded patch code.
old-location: image\wia_patch_code_info.htm
old-project: image
ms.assetid: 476C9269-7A88-4D06-80E8-C80E5F29B6CF
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WIA_PATCH_CODE_INFO, WIA_PATCH_CODE_INFO structure [Imaging Devices], _WIA_PATCH_CODE_INFO, image.wia_patch_code_info, wiadef/WIA_PATCH_CODE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wiadef.h
req.include-header: Wiadef.h
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
-	wiadef.h
api_name:
-	WIA_PATCH_CODE_INFO
product: Windows
targetos: Windows
req.typenames: WIA_PATCH_CODE_INFO
req.product: Windows 10 or later.
---

# _WIA_PATCH_CODE_INFO structure
The <b>WIA_PATCH_CODE_INFO</b> structure stores information for one decoded patch code.

## Syntax
````
typedef struct _WIA_PATCH_CODE_INFO {
  DWORD Type;
  DWORD Page;
} WIA_PATCH_CODE_INFO;
````

## Members


`Type`

The patch code type. One of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706269">WIA_IPS_SUPPORTED_PATCH_CODE_TYPES</a> values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wiadef.h (include Wiadef.h) |