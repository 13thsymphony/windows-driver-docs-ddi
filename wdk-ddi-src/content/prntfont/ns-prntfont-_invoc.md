---
UID : NS:prntfont._INVOC
title : _INVOC
author : windows-driver-content
description : The INVOC structure is used for describing printer command strings in Unidrv font metrics files (.ufm files) and glyph translation table files (.gtt files).
old-location : print\invoc.htm
old-project : print
ms.assetid : 5eeaa7f7-dc99-4cf7-846c-801954cc9040
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : _INVOC, print_unidrv-pscript_fonts_1c5bebe8-a2ca-4049-bcce-defd8622761b.xml, prntfont/PINVOC, prntfont/INVOC, PINVOC, INVOC structure [Print Devices], *PINVOC, print.invoc, INVOC, PINVOC structure pointer [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : prntfont.h
req.include-header : Prntfont.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : INVOC, *PINVOC
req.product : Windows 10 or later.
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

## Remarks
INVOC structures are used within <a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a> structures.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | prntfont.h (include Prntfont.h) |

## See Also

<a href="..\prntfont\ns-prntfont-_unidrvinfo.md">UNIDRVINFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20INVOC structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>