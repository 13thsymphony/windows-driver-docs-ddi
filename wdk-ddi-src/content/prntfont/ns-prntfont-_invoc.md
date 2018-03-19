---
UID: NS:prntfont._INVOC
title: "_INVOC"
author: windows-driver-content
description: The INVOC structure is used for describing printer command strings in Unidrv font metrics files (.ufm files) and glyph translation table files (.gtt files).
old-location: print\invoc.htm
old-project: print
ms.assetid: 5eeaa7f7-dc99-4cf7-846c-801954cc9040
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PINVOC, INVOC, INVOC structure [Print Devices], PINVOC, PINVOC structure pointer [Print Devices], _INVOC, print.invoc, print_unidrv-pscript_fonts_1c5bebe8-a2ca-4049-bcce-defd8622761b.xml, prntfont/INVOC, prntfont/PINVOC"
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
-	INVOC
product: Windows
targetos: Windows
req.typenames: INVOC, *PINVOC
req.product: Windows 10 or later.
---

# _INVOC structure
The INVOC structure is used for describing printer command strings in <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">Unidrv font metrics files</a> (.ufm files) and <a href="https://msdn.microsoft.com/6e643703-ace1-4660-990c-3a9ca735829d">glyph translation table files</a> (.gtt files).

## Syntax
````
typedef struct _INVOC {
  DWORD dwCount;
  DWORD loOffset;
} INVOC, *PINVOC;
````

## Members


`dwCount`

Specifies the number of characters in the command.

`loOffset`

Indicates one of the following:





##### ufm files:

Specifies the byte offset from the beginning of the .ufm file's <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structure to beginning of the command string.



##### gtt files:

Specifies the byte offset from the beginning of the .gtt file's <a href="..\prntfont\ns-prntfont-_uni_codepageinfo.md">UNI_CODEPAGEINFO</a> structure to beginning of the command string.

## Remarks
INVOC structures are used within <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a>