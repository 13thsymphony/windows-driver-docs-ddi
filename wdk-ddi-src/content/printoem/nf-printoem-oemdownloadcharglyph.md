---
UID: NF:printoem.OEMDownloadCharGlyph
title: OEMDownloadCharGlyph function
author: windows-driver-content
description: OEMDownloadCharGlyph function
old-location: print\oemdownloadcharglyph.htm
old-project: print
ms.assetid: da9a4058-1a0e-484b-afcd-9d4558810acd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: OEMDownloadCharGlyph, OEMDownloadCharGlyph function [Print Devices], print.oemdownloadcharglyph, print_obsoletefunctions_fb2af04d-799c-419c-b675-3444fd7d3143.xml, printoem/OEMDownloadCharGlyph
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printoem.h
req.include-header: Printoem.h
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
-	printoem.h
api_name:
-	OEMDownloadCharGlyph
product: Windows
targetos: Windows
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---


# OEMDownloadCharGlyph function


## Syntax

````
DWORD APIENTRY OEMDownloadCharGlyph(
        PDEVOBJ     pdevobj,
        PUNIFONTOBJ pUFObj,
        HGLYPH      hGlyph,
  _Out_ PDWORD      pdwWidth
);
````

## Parameters

`pdevobj`



`pUFObj`



`hGlyph`



`pdwWidth`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printoem.h (include Printoem.h) |