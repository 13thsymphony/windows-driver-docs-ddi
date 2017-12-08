---
UID: NS.PRNTFONT._UNI_GLYPHSETDATA
title: _UNI_GLYPHSETDATA
author: windows-driver-content
description: The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\uni_glyphsetdata.htm
old-project: print
ms.assetid: a2c98783-c463-435e-9d78-c10686f1c75c
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: _UNI_GLYPHSETDATA, *PUNI_GLYPHSETDATA, UNI_GLYPHSETDATA
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
req.alt-api: UNI_GLYPHSETDATA
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
req.product: Windows 10 or later.
---

# _UNI_GLYPHSETDATA structure



## -description
The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of <a href="print.customized_font_management#ddk_glyph_translation_table_files_gg#ddk_glyph_translation_table_files_gg">glyph translation table files</a> (.gtt files).


## -syntax

````
typedef struct _UNI_GLYPHSETDATA {
  DWORD dwSize;
  DWORD dwVersion;
  DWORD dwFlags;
  LONG  lPredefinedID;
  DWORD dwGlyphCount;
  DWORD dwRunCount;
  DWORD loRunOffset;
  DWORD dwCodePageCount;
  DWORD loCodePageOffset;
  DWORD loMapTableOffset;
  DWORD dwReserved[2];
} UNI_GLYPHSETDATA, *PUNI_GLYPHSETDATA;
````


## -struct-fields

### -field dwSize

Specifies the total size, in bytes, of the .gtt file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNI_GLYPHSETDATA structure.

### -field dwVersion

Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNI_GLYPHSETDATA_VERSION_<i>x</i>_<i>x</i>.

### -field dwFlags

Not used.

### -field lPredefinedID

Specifies one of the CC_-prefixed code conversion identifiers defined in prntfont.h. 

### -field dwGlyphCount

Specifies the number of glyphs provided by this font.

### -field dwRunCount

Specifies the number of <a href="print.glyphrun">GLYPHRUN</a> structures in the array pointed to by <b>loRunOffset</b>.

### -field loRunOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="print.glyphrun">GLYPHRUN</a> structures.

### -field dwCodePageCount

Specifies the number of <a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a> structures in the array pointed to by <b>loCodePageOffset</b>.

### -field loCodePageOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a> structures.

### -field loMapTableOffset

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of a <a href="print.maptable">MAPTABLE</a> structure.

### -field dwReserved

Reserved for system use.

## -remarks
A UNI_GLYPHSETDATA structure must be the first structure contained in a .gtt file.

## -requirements
<table>
<tr>
<th width="30%">
Header
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
<a href="print.glyphrun">GLYPHRUN</a>
</dt>
<dt>
<a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a>
</dt>
<dt>
<a href="print.maptable">MAPTABLE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20UNI_GLYPHSETDATA structure%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
