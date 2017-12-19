---
UID: NS.PRNTFONT._MAPTABLE
title: _MAPTABLE
author: windows-driver-content
description: The MAPTABLE structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\maptable.htm
old-project: print
ms.assetid: d3dcf7b0-4244-41c1-801e-cf41b20f2d54
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _MAPTABLE, *PMAPTABLE, MAPTABLE, PMAPTABLE
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
req.alt-api: MAPTABLE
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

# _MAPTABLE structure



## -description
The MAPTABLE structure is one of the structures used to define the contents of <a href="print.customized_font_management#ddk_glyph_translation_table_files_gg#ddk_glyph_translation_table_files_gg">glyph translation table files</a> (.gtt files).



## -syntax

````
typedef struct _MAPTABLE {
  DWORD     dwSize;
  DWORD     dwGlyphNum;
  TRANSDATA Trans[1];
} MAPTABLE, *PMAPTABLE;
````


## -struct-fields

### -field dwSize

Specifies the size, in bytes, of the MAPTABLE structure, including the <b>Trans</b> array.


### -field dwGlyphNum

Specifies the number of elements in the <b>Trans</b> array.


### -field Trans

Is an array of <a href="print.transdata">TRANSDATA</a> structures.


## -remarks
A .gtt file's MAPTABLE structure, which contains a glyph mapping table, is accessed by a pointer in the file's <a href="print.uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure. The table maps glyph handles to the character codes or commands that must be sent to the printer in order to print glyphs.


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
<a href="print.transdata">TRANSDATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20MAPTABLE structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

