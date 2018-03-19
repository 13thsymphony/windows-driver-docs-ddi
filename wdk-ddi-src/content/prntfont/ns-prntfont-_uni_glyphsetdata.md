---
UID: NS:prntfont._UNI_GLYPHSETDATA
title: "_UNI_GLYPHSETDATA"
author: windows-driver-content
description: The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of glyph translation table files (.gtt files).
old-location: print\uni_glyphsetdata.htm
old-project: print
ms.assetid: a2c98783-c463-435e-9d78-c10686f1c75c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PUNI_GLYPHSETDATA, PUNI_GLYPHSETDATA, PUNI_GLYPHSETDATA structure pointer [Print Devices], UNI_GLYPHSETDATA, UNI_GLYPHSETDATA structure [Print Devices], _UNI_GLYPHSETDATA, print.uni_glyphsetdata, print_unidrv-pscript_fonts_51c5f97c-3b3c-4990-8dcb-9c7bf387b03f.xml, prntfont/PUNI_GLYPHSETDATA, prntfont/UNI_GLYPHSETDATA"
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
-	UNI_GLYPHSETDATA
product: Windows
targetos: Windows
req.typenames: UNI_GLYPHSETDATA, *PUNI_GLYPHSETDATA
req.product: Windows 10 or later.
---

# _UNI_GLYPHSETDATA structure
The UNI_GLYPHSEDATA structure is one of the structures used to define the contents of <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).

## Syntax
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

## Members


`dwSize`

Specifies the total size, in bytes, of the .gtt file. Note that this is the total size of all structures used to define the file. This value is not the size of the UNI_GLYPHSETDATA structure.

`dwVersion`

Specifies the file version number, as defined in prntfont.h by a constant with a name format of UNI_GLYPHSETDATA_VERSION_<i>x</i>_<i>x</i>.

`dwFlags`

Not used.

`lPredefinedID`

Specifies one of the CC_-prefixed code conversion identifiers defined in prntfont.h.

`dwGlyphCount`

Specifies the number of glyphs provided by this font.

`dwRunCount`

Specifies the number of <a href="..\prntfont\ns-prntfont-_glyphrun.md">GLYPHRUN</a> structures in the array pointed to by <b>loRunOffset</b>.

`loRunOffset`

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="..\prntfont\ns-prntfont-_glyphrun.md">GLYPHRUN</a> structures.

`dwCodePageCount`

Specifies the number of <a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a> structures in the array pointed to by <b>loCodePageOffset</b>.

`loCodePageOffset`

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of an array of <a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a> structures.

`loMapTableOffset`

Specifies the byte offset from the beginning of the UNI_GLYPHSETDATA structure to the beginning of a <a href="..\prntfont\ns-prntfont-_maptable.md">MAPTABLE</a> structure.

`dwReserved`

Reserved for system use.

## Remarks
A UNI_GLYPHSETDATA structure must be the first structure contained in a .gtt file.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_maptable.md">MAPTABLE</a>



<a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a>



<a href="..\prntfont\ns-prntfont-_glyphrun.md">GLYPHRUN</a>