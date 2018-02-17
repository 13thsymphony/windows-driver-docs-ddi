---
UID: NS:prntfont._WIDTHRUN
title: "_WIDTHRUN"
author: windows-driver-content
description: The WIDTHRUN structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\widthrun.htm
old-project: print
ms.assetid: 18cc608e-b94d-4588-98e9-c22a7949a3b6
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: prntfont/PWIDTHRUN, WIDTHRUN structure [Print Devices], WIDTHRUN, *PWIDTHRUN, prntfont/WIDTHRUN, PWIDTHRUN, PWIDTHRUN structure pointer [Print Devices], _WIDTHRUN, print_unidrv-pscript_fonts_68b08066-7503-4496-bfab-001aba659926.xml, print.widthrun
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
-	WIDTHRUN
product: Windows
targetos: Windows
req.typenames: "*PWIDTHRUN, WIDTHRUN"
req.product: Windows 10 or later.
---

# _WIDTHRUN structure
The WIDTHRUN structure is used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font metrics files</a> (.ufm files).

## Syntax
````
typedef struct _WIDTHRUN {
  WORD  wStartGlyph;
  WORD  wGlyphCount;
  DWORD loCharWidthOffset;
} WIDTHRUN, *PWIDTHRUN;
````

## Members


`loCharWidthOffset`

Specifies the offset from the beginning of a <a href="..\prntfont\ns-prntfont-_widthtable.md">WIDTHTABLE</a> structure to the location containing the width of the set of glyphs contained in the width run.

`wGlyphCount`

Specifies the number of glyphs represented by the width run.

`wStartGlyph`

Is an index value indicating the first glyph of the width run.

## Remarks
A width run describes the widths of a set of adjacent glyphs. Sets of width runs are described by an array of WIDTHRUN elements. The array is contained in a <a href="..\prntfont\ns-prntfont-_widthtable.md">WIDTHTABLE</a> structure.

Index values contained in <b>dwStartGlyph</b> are integers, starting with 1, with each glyph in the font having an index. That is, the first glyph in the font is assigned an index value of 1, the next glyph's index is 2, and so on.

For example, suppose the first three elements of a WIDTHRUN array contain the following values:

<b>wStartGlyph</b>
<b>wGlyphCount</b>
<b>IoCharWidthOffset</b>=<i>xxx</i>

<b>wStartGlyph</b>
<b>wGlyphCount</b>
<b>IoCharWidthOffset</b>=<i>yyy</i>

<b>wStartGlyph</b>
<b>wGlyphCount</b>
<b>IoCharWidthOffset</b>
<i>zzz</i>
At offset <i>xxx</i>: 56, 50, 60 (WORD-sized)

At offset <i>yyy</i>: 54, 60

At offset <i>zzz</i>: 54, 60, 43, 40

In this example, widths for the first three glyphs of the font are contained in an array at location WIDTHTABLE+<i>xxx</i>, the widths for the next two glyphs are contained in an array at location WIDTHTABLE+<i>yyy</i>, and widths for the next four glyphs are contained in an array at location WIDTHTABLE+<i>zzz</i>.

If a device font is proportional and has variable pitch characters, the WIDTHTABLE structure's <b>WidthRun</b> array contains only one WIDTHRUN element, and WIDTHTABLE+<b>loCharWidthOffset</b> points to a character width array for all characters in the font.

For Western device fonts, the <b>fwdAveCharWidth</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567418">IFIMETRICS</a> structure is used for determining single-byte character widths, if the character widths are not specified using a WIDTHTABLE structure.

For East Asian device fonts, the <b>fwdAveCharWidth</b> and <b>fwdMaxCharInc</b> members of the IFIMETRICS structure are used for determining single-byte and double-byte character widths. If the font is proportional, the font's .ufm file should contain a WIDTHTABLE structure for the proportional glyphs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_widthtable.md">WIDTHTABLE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567418">IFIMETRICS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WIDTHRUN structure%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>