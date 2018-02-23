---
UID: NS:wiadef._WIA_MICR
title: "_WIA_MICR"
author: windows-driver-content
description: The WIA_MICR structure stores header information for the MICR metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_micr.htm
old-project: Image
ms.assetid: CAD08405-698C-4C3A-A03F-827837199CC8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_WIA_MICR, WIA_MICR, image.wia_micr, WIA_MICR structure [Imaging Devices], wiadef/WIA_MICR"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wiadef.h
apiname:
-	WIA_MICR
product: Windows
targetos: Windows
req.typenames: WIA_MICR
req.product: Windows 10 or later.
---

# _WIA_MICR structure
The <b>WIA_MICR</b> structure stores header information for the MICR metadata report of one scan job (one call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543956">IWiaMiniDrv::drvAcquireItemData</a>).

## Syntax
````
typedef struct _WIA_MICR {
  DWORD         Tag;
  DWORD         Version;
  DWORD         Size;
  WCHAR         Placeholder;
  DWORD         Count;
  WIA_MICR_INFO Micr[1];
} WIA_MICR;
````

## Members


`Count`

Specifies the number of <a href="..\wiadef\ns-wiadef-_wia_micr_info.md">WIA_MICR_INFO</a> elements in the <b>Micr</b> sequence.

`Micr`

Placeholder for a sequence of <b>Count</b> contiguous <a href="..\wiadef\ns-wiadef-_wia_micr_info.md">WIA_MICR_INFO</a> structures.

`Placeholder`

Placeholder for unrecognized characters.

`Reserved`



`Size`

The complete size of this <b>WIA_MICR</b> header structure, in bytes, including the complete size of the <a href="..\wiadef\ns-wiadef-_wia_micr_info.md">WIA_MICR_INFO</a> list.

`Tag`

Must be the literal 'WMIC', 4 single byte ASCII characters.

`Version`

Must be the value 0x00010000 (Version 1.0).

## Remarks
The header must be followed by a sequence of MICR information structures, one for each decoded MICR code, in the order the MICR codes were found and decoded.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wiadef.h (include Wiadef.h) |