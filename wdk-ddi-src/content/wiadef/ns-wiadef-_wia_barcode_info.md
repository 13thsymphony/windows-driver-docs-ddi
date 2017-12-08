---
UID: NS.WIADEF._WIA_BARCODE_INFO
title: _WIA_BARCODE_INFO
author: windows-driver-content
description: The WIA_BARCODE_INFO structure stores information for one decoded barcode.
old-location: image\wia_barcode_info.htm
old-project: image
ms.assetid: 2E659DDC-4012-4EA2-8E6C-033F2AB526B8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WIA_BARCODE_INFO, WIA_BARCODE_INFO
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
req.alt-api: WIA_BARCODE_INFO
req.alt-loc: wiadef.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# _WIA_BARCODE_INFO structure



## -description
The <b>WIA_BARCODE_INFO</b> structure stores information for one decoded barcode.


## -syntax

````
typedef struct _WIA_BARCODE_INFO {
  DWORD Size;
  DWORD Type;
  DWORD Page;
  DWORD Confidence;
  DWORD Xoffset;
  DWORD Yoffset;
  DWORD Rotation;
  DWORD Length;
  WCHAR Text[1];
} WIA_BARCODE_INFO;
````


## -struct-fields

### -field Size

The total size of this structure, in bytes.

### -field Type

The barcode type. One of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh706268">WIA_IPS_SUPPORTED_BARCODE_TYPES</a> values.

### -field Page

The page number where the barcode was detected. A zero-based index referring to the current scan job.

### -field Confidence

The confidence level. A value in the range from 0 (no confidence) to 10 (maximum confidence).

### -field Xoffset

The horizontal coordinate, in pixels (relative to the scanned image), where the top-left origin of the barcode was detected. This value can be 0 if it is unknown.

### -field Yoffset

The vertical coordinate, in pixels (relative to the scanned image), where the top-left origin of the barcode was detected. This value can be 0 if it is unknown.

### -field Rotation

The rotation of the barcode, in degrees. A value in the rage from 0 to 359. This value can be 0 if it is unknown.

### -field Length

The number of text characters in the character string containing the decoded barcode text, excluding the length of the NULL terminator.

### -field Text

Placeholder for the character string containing the decoded barcode text (double byte characters, NULL terminated).

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wiadef.h (include Wiadef.h)</dt>
</dl>
</td>
</tr>
</table>