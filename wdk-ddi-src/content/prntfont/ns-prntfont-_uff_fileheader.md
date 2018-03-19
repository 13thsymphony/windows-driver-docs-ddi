---
UID: NS:prntfont._UFF_FILEHEADER
title: "_UFF_FILEHEADER"
author: windows-driver-content
description: The UFF_FILEHEADER structure is used to define the contents of Unidrv font format files (.uff files).
old-location: print\uff_fileheader.htm
old-project: print
ms.assetid: 18eb526b-d615-4f02-b724-236c6bf16945
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUFF_FILEHEADER, PUFF_FILEHEADER, PUFF_FILEHEADER structure pointer [Print Devices], UFF_FILEHEADER, UFF_FILEHEADER structure [Print Devices], _UFF_FILEHEADER, print.uff_fileheader, print_unidrv-pscript_fonts_a51bc6b1-df89-423f-83e8-9fad0cd20729.xml, prntfont/PUFF_FILEHEADER, prntfont/UFF_FILEHEADER"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	prntfont.h
api_name:
-	UFF_FILEHEADER
product: Windows
targetos: Windows
req.typenames: UFF_FILEHEADER, *PUFF_FILEHEADER
req.product: Windows 10 or later.
---

# _UFF_FILEHEADER structure
The UFF_FILEHEADER structure is used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font format files</a> (.uff files).

## Syntax
````
typedef struct _UFF_FILEHEADER {
  DWORD dwSignature;
  DWORD dwVersion;
  DWORD dwSize;
  DWORD nFonts;
  DWORD nGlyphSets;
  DWORD nVarData;
  DWORD offFontDir;
  DWORD dwFlags;
  DWORD dwReserved[4];
} UFF_FILEHEADER, *PUFF_FILEHEADER;
````

## Members


`dwSignature`

Specifies the signature for .uff files. This value must be UFF_FILE_MAGIC.

`dwVersion`

Specifies the format version for .uff files. This value must be UFF_VERSION_NUMBER. The HIWORD contains the major version number and the LOWORD contains the minor version number.

`dwSize`

Specifies the size, in bytes, of the UFF_FILEHEADER structure.

`nFonts`

Specifies the number of fonts specified within the .uff file and identified by <a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a> structures. This is also the number of <a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a> structures within the .uff file.

`nGlyphSets`

Specifies the  number of glyph sets specified within the .uff file and identified by DATA_HEADER structures. Some fonts might share a glyph set.

`nVarData`

Specifies the  number of variable data sections specified within the .uff file and identified by DATA_HEADER structures.

`offFontDir`

Specifies the offset, in bytes, from the beginning of the .uff file to the beginning of the first <a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a> structure.

`dwFlags`

Is a set of bit flags, as specified in the following table.

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
FONT_DIR_SORTED

</td>
<td>
The array of UFF_FONTDIRECTORY structures (specified by <b>offFontDir</b>) is sorted by the contents of that structure's <b>wFontID</b> member.

</td>
</tr>
</table>

`dwReserved`

Reserved. Must be set to zero.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_uff_fontdirectory.md">UFF_FONTDIRECTORY</a>



<a href="..\prntfont\ns-prntfont-_data_header.md">DATA_HEADER</a>