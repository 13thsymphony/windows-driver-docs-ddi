---
UID: NS.prntfont._WIDTHRUN
title: WIDTHRUN
author: windows-driver-content
description: The WIDTHRUN structure is used to define the contents of Unidrv font metrics files (.ufm files).
old-location: print\widthrun.htm
old-project: print
ms.assetid: 18cc608e-b94d-4588-98e9-c22a7949a3b6
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: WIDTHRUN, WIDTHRUN, *PWIDTHRUN
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
req.alt-api: WIDTHRUN
req.alt-loc: prntfont.h
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
req.iface: 
req.product: Windows 10 or later.
---

# WIDTHRUN structure



## -description
<p>The WIDTHRUN structure is used to define the contents of <a href="print.customized_font_management#ddk_unidrv_font_metrics_files_gg#ddk_unidrv_font_metrics_files_gg">Unidrv font metrics files</a> (.ufm files).</p>


## -syntax

````
typedef struct _WIDTHRUN {
  WORD  wStartGlyph;
  WORD  wGlyphCount;
  DWORD loCharWidthOffset;
} WIDTHRUN, *PWIDTHRUN;
````


## -struct-fields
<dl>

### -field <b>wStartGlyph</b>

<dd>
<p>Is an index value indicating the first glyph of the width run.</p>
</dd>

### -field <b>wGlyphCount</b>

<dd>
<p>Specifies the number of glyphs represented by the width run.</p>
</dd>

### -field <b>loCharWidthOffset</b>

<dd>
<p>Specifies the offset from the beginning of a <a href="..\prntfont\ns-prntfont--widthtable.md">WIDTHTABLE</a> structure to the location containing the width of the set of glyphs contained in the width run.</p>
</dd>
</dl>

## -remarks
<p>A width run describes the widths of a set of adjacent glyphs. Sets of width runs are described by an array of WIDTHRUN elements. The array is contained in a <a href="..\prntfont\ns-prntfont--widthtable.md">WIDTHTABLE</a> structure.</p>

<p>Index values contained in <b>dwStartGlyph</b> are integers, starting with 1, with each glyph in the font having an index. That is, the first glyph in the font is assigned an index value of 1, the next glyph's index is 2, and so on.</p>

<p>For example, suppose the first three elements of a WIDTHRUN array contain the following values:</p>

<p><b>IoCharWidthOffset</b>=<i>xxx</i></p>

<p><b>IoCharWidthOffset</b>=<i>yyy</i></p>

<p>At offset <i>xxx</i>: 56, 50, 60 (WORD-sized)</p>

<p>At offset <i>yyy</i>: 54, 60</p>

<p>At offset <i>zzz</i>: 54, 60, 43, 40</p>

<p>In this example, widths for the first three glyphs of the font are contained in an array at location WIDTHTABLE+<i>xxx</i>, the widths for the next two glyphs are contained in an array at location WIDTHTABLE+<i>yyy</i>, and widths for the next four glyphs are contained in an array at location WIDTHTABLE+<i>zzz</i>.</p>

<p>If a device font is proportional and has variable pitch characters, the WIDTHTABLE structure's <b>WidthRun</b> array contains only one WIDTHRUN element, and WIDTHTABLE+<b>loCharWidthOffset</b> points to a character width array for all characters in the font.</p>

<p>For Western device fonts, the <b>fwdAveCharWidth</b> member of the <a href="display.ifimetrics">IFIMETRICS</a> structure is used for determining single-byte character widths, if the character widths are not specified using a WIDTHTABLE structure.</p>

<p>For East Asian device fonts, the <b>fwdAveCharWidth</b> and <b>fwdMaxCharInc</b> members of the IFIMETRICS structure are used for determining single-byte and double-byte character widths. If the font is proportional, the font's .ufm file should contain a WIDTHTABLE structure for the proportional glyphs.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prntfont.h (include Prntfont.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\prntfont\ns-prntfont--widthtable.md">WIDTHTABLE</a>
</dt>
<dt>
<a href="display.ifimetrics">IFIMETRICS</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20WIDTHRUN structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
