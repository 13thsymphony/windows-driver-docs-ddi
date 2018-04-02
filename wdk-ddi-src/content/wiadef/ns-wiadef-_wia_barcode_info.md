---
UID: NS:wiadef._WIA_BARCODE_INFO
title: "_WIA_BARCODE_INFO"
author: windows-driver-content
description: The WIA_BARCODE_INFO structure stores information for one decoded barcode.
old-location: image\wia_barcode_info.htm
old-project: image
ms.assetid: 2E659DDC-4012-4EA2-8E6C-033F2AB526B8
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: WIA_BARCODE_INFO, WIA_BARCODE_INFO structure [Imaging Devices], _WIA_BARCODE_INFO, image.wia_barcode_info, wiadef/WIA_BARCODE_INFO
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
req.idl: WDTFSystemAction.idl
req.max-support: 
req.namespace: Microsoft.WDTF
req.assembly: WDTFSystemAction.Interop.dll
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
-	WIA_BARCODE_INFO
product: Windows
targetos: Windows
req.typenames: WIA_BARCODE_INFO
req.product: Windows 10 or later.
---

# _WIA_BARCODE_INFO structure
The <b>WIA_BARCODE_INFO</b> structure stores information for one decoded barcode.

## Syntax
```
typedef struct _WIA_BARCODE_INFO {
  DWORD Size;
  DWORD Type;
  DWORD Page;
  DWORD Confidence;
  DWORD XOffset;
  DWORD YOffset;
  DWORD Rotation;
  DWORD Length;
  WCHAR Text[1];
} WIA_BARCODE_INFO;
```

## Members


`Size`

The total size of this structure, in bytes.

`Type`

The barcode type. One of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706268">WIA_IPS_SUPPORTED_BARCODE_TYPES</a> values.

`Page`

The page number where the barcode was detected. A zero-based index referring to the current scan job.

`Confidence`

The confidence level. A value in the range from 0 (no confidence) to 10 (maximum confidence).

`XOffset`



`YOffset`



`Rotation`

The rotation of the barcode, in degrees. A value in the rage from 0 to 359. This value can be 0 if it is unknown.

`Length`

The number of text characters in the character string containing the decoded barcode text, excluding the length of the NULL terminator.

`Text`

Placeholder for the character string containing the decoded barcode text (double byte characters, NULL terminated).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wiadef.h (include Wiadef.h) |