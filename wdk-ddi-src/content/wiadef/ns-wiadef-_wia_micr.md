---
UID: NS.WIADEF._WIA_MICR
title: _WIA_MICR
author: windows-driver-content
description: The WIA_MICR structure stores header information for the MICR metadata report of one scan job (one call to IWiaMiniDrv::drvAcquireItemData).
old-location: image\wia_micr.htm
old-project: image
ms.assetid: CAD08405-698C-4C3A-A03F-827837199CC8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WIA_MICR, WIA_MICR
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
req.alt-api: WIA_MICR
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

# _WIA_MICR structure



## -description
The <b>WIA_MICR</b> structure stores header information for the MICR metadata report of one scan job (one call to <a href="image.iwiaminidrv_drvacquireitemdata">IWiaMiniDrv::drvAcquireItemData</a>).



## -syntax

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


## -struct-fields

### -field Tag

Must be the literal 'WMIC', 4 single byte ASCII characters. 


### -field Version

Must be the value 0x00010000 (Version 1.0).


### -field Size

The complete size of this <b>WIA_MICR</b> header structure, in bytes, including the complete size of the <a href="image.wia_micr_info">WIA_MICR_INFO</a> list.


### -field Placeholder

Placeholder for unrecognized characters.


### -field Count

Specifies the number of <a href="image.wia_micr_info">WIA_MICR_INFO</a> elements in the <b>Micr</b> sequence.


### -field Micr

Placeholder for a sequence of <b>Count</b> contiguous <a href="image.wia_micr_info">WIA_MICR_INFO</a> structures.


## -remarks
The header must be followed by a sequence of MICR information structures, one for each decoded MICR code, in the order the MICR codes were found and decoded.


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