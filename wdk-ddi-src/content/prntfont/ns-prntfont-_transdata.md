---
UID: NS.PRNTFONT._TRANSDATA
title: _TRANSDATA
author: windows-driver-content
description: The TRANSDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\transdata.htm
old-project: print
ms.assetid: 75ddf007-0113-4967-a8d4-02fcc3cc2857
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: _TRANSDATA, *PTRANSDATA, TRANSDATA
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
req.alt-api: TRANSDATA
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

# _TRANSDATA structure



## -description
The TRANSDATA structure is one of the structures used to define the contents of <a href="print.customized_font_management#ddk_glyph_translation_table_files_gg#ddk_glyph_translation_table_files_gg">glyph translation table files</a> (.gtt files).



## -syntax

````
typedef struct _TRANSDATA {
  BYTE  ubCodePageID;
  BYTE  ubType;
  union {
    SHORT sCode;
    BYTE  ubCode;
    BYTE  ubPairs[2];
  } uCode;
} TRANSDATA, *PTRANSDATA;
````


## -struct-fields

### -field ubCodePageID

Specifies the zero-based index of a particular structure in the array of <a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a> structures. The first structure in this array has an index of 0, the second structure has an index of 1, and so on.

The <b>loCodePageOffset</b> member of the <a href="print.uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure contains the offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of the array of UNI_CODEPAGEINFO structures.


### -field ubType

Is a set of one or more bit flags, as follows:

<table>
<tr>
<th colspan="2">Flag</th>
<th>Definition</th>
</tr>
<tr>
<td colspan="2">
<b>Format Flags</b>

</td>
<td>
One of the following three flags can be set.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_COMPOSE

</td>
<td>
The <b>sCode</b> member of the <b>uCode</b> union contains an offset to a string. The string contains a command to be sent to the printer.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_DIRECT

</td>
<td>
The <b>ubCode</b> member of the <b>uCode</b> union contains a one-byte character code to be sent to the printer.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_PAIRED

</td>
<td>
The <b>ubPairs</b> member of the <b>uCode</b> union contains a two-byte character code to be sent to the printer.

</td>
</tr>
<tr>
<td colspan="2">
<b>Action Flags</b>

</td>
<td>
One of the following flags can be set. All are optional. Not valid if the <b>lPredefinedID</b> member of the <a href="print.uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure is set to CC_NOPRECNV.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_ADD

</td>
<td>
The specified mapping is added to the map table contained in the .gtt file specified by the <b>lPredefinedID</b> member of the UNI_GLYPHSETDATA structure.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_DISABLE

</td>
<td>
The specified mapping, contained in the .gtt file specified by the <b>lPredefinedID</b> member of the <a href="print.uni_glyphsetdata">UNI_GLYPHSETDATA</a> structure, is disabled.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_REPLACE

</td>
<td>
The specified mapping replaces mapping in the map table contained in the .gtt file specified by the <b>lPredefinedID</b> member of the UNI_GLYPHSETDATA structure.

</td>
</tr>
<tr>
<td colspan="2">
<b>East Asian Flags</b>

</td>
<td>
One of the following flags can be set.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_SINGLE

</td>
<td>
Character data is single-byte.

</td>
</tr>
<tr>
<td></td>
<td>
MTYPE_DOUBLE

</td>
<td>
Character data is double-byte.

</td>
</tr>
</table>
 


### -field uCode


### -field sCode

Specifies the offset to a command string. The offset is relative to the beginning of the <a href="print.maptable">MAPTABLE</a> structure containing the TRANSDATA array. The first word of the command string must be the command size. Valid if the MTYPE_COMPOSE flag is set in <b>uType</b>.


### -field ubCode

Specifies a one-byte character code. Valid if the MTYPE_DIRECT flag is set in <b>uType</b>.


### -field ubPairs

Specifies a two-byte character code. Valid if the MTYPE_PAIRED flag is set in <b>uType</b>.

</dd>
</dl>

## -remarks
A .gtt file's TRANSDATA structure array, which contains glyph mapping information, is contained in the file's <a href="print.maptable">MAPTABLE</a> structure.


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
<a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a>
</dt>
<dt>
<a href="print.uni_glyphsetdata">UNI_GLYPHSETDATA</a>
</dt>
<dt>
<a href="print.maptable">MAPTABLE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20TRANSDATA structure%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

