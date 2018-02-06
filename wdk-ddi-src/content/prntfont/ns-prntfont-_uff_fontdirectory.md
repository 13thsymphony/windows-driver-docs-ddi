---
UID: NS:prntfont._UFF_FONTDIRECTORY
title: "_UFF_FONTDIRECTORY"
author: windows-driver-content
description: The UFF_FONTDIRECTORY structure is used to specify the directory of font descriptions contained in a Unidrv font format file (.uff file).
old-location: print\uff_fontdirectory.htm
old-project: print
ms.assetid: d1cde8a4-f27b-440c-bfb1-c9a564c59c04
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.uff_fontdirectory, UFF_FONTDIRECTORY structure [Print Devices], PUFF_FONTDIRECTORY structure pointer [Print Devices], prntfont/UFF_FONTDIRECTORY, print_unidrv-pscript_fonts_979a2793-a3e4-4939-aab1-29510951b621.xml, PUFF_FONTDIRECTORY, _UFF_FONTDIRECTORY, UFF_FONTDIRECTORY, *PUFF_FONTDIRECTORY, prntfont/PUFF_FONTDIRECTORY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: prntfont.h
req.include-header: Prntfont.h
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
-	prntfont.h
apiname:
-	UFF_FONTDIRECTORY
product: Windows
targetos: Windows
req.typenames: UFF_FONTDIRECTORY, *PUFF_FONTDIRECTORY
req.product: Windows 10 or later.
---

# _UFF_FONTDIRECTORY structure
The UFF_FONTDIRECTORY structure is used to specify the directory of font descriptions contained in a Unidrv font format file (.uff file).

## Syntax
````
typedef struct _UFF_FONTDIRECTORY {
  DWORD dwSignature;
  WORD  wSize;
  WORD  wFontID;
  SHORT sGlyphID;
  WORD  wFlags;
  DWORD dwInstallerSig;
  DWORD offFontName;
  DWORD offCartridgeName;
  DWORD offFontData;
  DWORD offGlyphData;
  DWORD offVarData;
} UFF_FONTDIRECTORY, *PUFF_FONTDIRECTORY;
````

## Members


`dwInstallerSig`

Specifies the signature value of the font installer that installed the font.

`dwSignature`

Specifies the font metrics record signature. This value must be FONT_REC_SIG.

`offCartridgeName`

Specifies the offset, in bytes, from the beginning of the .uff file to a DWORD-aligned, NULL-terminated, Unicode string representing the name of the font cartridge containing the font. If the font is not contained in a cartridge, this value should be zero.

`offFontData`

Specifies the offset, in bytes, from the beginning of the .uff file to a DWORD-aligned <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structure specifying a font metrics section.

`offFontName`

Specifies the offset, in bytes, from the beginning of the .uff file to a DWORD-aligned, NULL-terminated, Unicode string representing the name of the font.

`offGlyphData`

Specifies the offset, in bytes, from the beginning of the .uff file to a DWORD-aligned DATA_HEADER structure specifying a glyph set section. If <b>sGlyphID</b> is zero or negative, <b>offGlyphData</b> should be zero.

`offVarData`

Specifies the offset, in bytes, from the beginning of the .uff file to a DWORD-aligned <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structure specifying a data section. If the FONT_FL_PERMANENT_SF flag is set in <b>wFlags</b>, <b>offVarData</b> must be zero.

`sGlyphID`

Specifies the glyph set identifier. This value specifies the glyph set that is to be associated with the font. See the following Remarks section.

`wFlags`

Is a set of bit flags. One or more of the following flags can be specified.
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
FONT_FL_DEVICEFONT

</td>
<td>
The font is a device font.

</td>
</tr>
<tr>
<td>
FONT_FL_GLYPHSET_GTT

</td>
<td>
The glyph set is specified in Windows 2000 and later <a href="https://msdn.microsoft.com/f67c673d-c6f0-49f0-850a-d8b00e99ddd4">GTT</a> format.

</td>
</tr>
<tr>
<td>
FONT_FL_GLYPHSET_RLE

</td>
<td>
The glyph set is specified in Windows NT 4.0 <a href="https://msdn.microsoft.com/004698f5-cb0e-4995-a19c-7075aa226000">RLE</a> format.

</td>
</tr>
<tr>
<td>
FONT_FL_IFI

</td>
<td>
Font metrics are specified in Windows NT 4.0 IFI format.

</td>
</tr>
<tr>
<td>
FONT_FL_PERMANENT_SF

</td>
<td>
The font is a PCL permanent soft font.

</td>
</tr>
<tr>
<td>
FONT_FL_SOFTFONT

</td>
<td>
The font is a <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">PCL</a> soft font.

</td>
</tr>
<tr>
<td>
FONT_FL_UFM

</td>
<td>
Font metrics are specified in Windows 2000 and later <a href="https://msdn.microsoft.com/0a51fa2b-3d09-4a5f-9fff-40604877a414">UFM</a> format.

</td>
</tr>
</table>

`wFontID`

Specifies the font identifier. This value must match the <b>wDataID</b> member of a <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structure that specifies font metrics information within the .uff file.

`wSize`

Specifies the size, in bytes, of the UFF_FONTDIRECTORY structure.

## Remarks
If <b>sGlyphID</b> is a greater than zero, it must match the <b>wDataID</b> member of a <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structure that specifies a glyph set within the .uff file.

If <b>sGlyphID</b> is less than zero, it must be one of the CC_-prefixed constants defined in prntfont.h, which identify predefined glyph sets.

If <b>sGlyphID</b> is zero, Unidrv uses the glyph set resource identifier contained in the font's UNIFM_HDR structure. The glyph set resource must be contained in the minidriver's resource DLL, or else Unidrv uses the default glyph translation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UFF_FONTDIRECTORY structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>