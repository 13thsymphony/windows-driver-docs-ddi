---
UID: NS.PRNTFONT._INVOC
title: _INVOC
author: windows-driver-content
description: The INVOC structure is used for describing printer command strings in Unidrv font metrics files (.ufm files) and glyph translation table files (.gtt files).
old-location: print\invoc.htm
old-project: print
ms.assetid: 5eeaa7f7-dc99-4cf7-846c-801954cc9040
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _INVOC, PINVOC, *PINVOC, INVOC
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
req.alt-api: INVOC
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

# _INVOC structure



## -description
The INVOC structure is used for describing printer command strings in <a href="print.customized_font_management#ddk_unidrv_font_metrics_files_gg#ddk_unidrv_font_metrics_files_gg">Unidrv font metrics files</a> (.ufm files) and <a href="print.customized_font_management#ddk_glyph_translation_table_files_gg#ddk_glyph_translation_table_files_gg">glyph translation table files</a> (.gtt files).



## -syntax

````
typedef struct _INVOC {
  DWORD dwCount;
  DWORD loOffset;
} INVOC, *PINVOC;
````


## -struct-fields

### -field dwCount

Specifies the number of characters in the command.


### -field loOffset

Indicates one of the following:




### -field For .ufm files:

Specifies the byte offset from the beginning of the .ufm file's <a href="print.unidrvinfo">UNIDRVINFO</a> structure to beginning of the command string.


### -field For .gtt files:

Specifies the byte offset from the beginning of the .gtt file's <a href="print.uni_codepageinfo">UNI_CODEPAGEINFO</a> structure to beginning of the command string.

</dd>
</dl>

## -remarks
INVOC structures are used within <a href="print.unidrvinfo">UNIDRVINFO</a> structures.


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
<a href="print.unidrvinfo">UNIDRVINFO</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20INVOC structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

