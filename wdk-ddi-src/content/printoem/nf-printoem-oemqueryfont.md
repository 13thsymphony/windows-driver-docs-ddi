---
UID: NF.printoem.OEMQueryFont
title: OEMQueryFont function
author: windows-driver-content
description: The OEMQueryFont function is used by GDI to get the IFIMETRICS structure for a given font.
old-location: print\oemqueryfont.htm
old-project: print
ms.assetid: cee6b2dd-e79b-4372-8371-c57fe950de88
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: OEMQueryFont
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
req.alt-api: OEMQueryFont
req.alt-loc: printoem.h
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

# OEMQueryFont function



## -description
The <code>OEMQueryFont</code> function is used by GDI to get the <a href="display.ifimetrics">IFIMETRICS</a> structure for a given font. 



## -syntax

````
PIFIMETRICS APIENTRY OEMQueryFont(
   DHPDEV    dhpdev,
   ULONG_PTR iFile,
   ULONG     iFace,
   ULONG_PTR *pid
);
````


## -parameters

### -param dhpdev 


### -param iFile 


### -param iFace 


### -param pid 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printoem.h (include Printoem.h)</dt>
</dl>
</td>
</tr>
</table>