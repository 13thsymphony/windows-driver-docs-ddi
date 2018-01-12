---
UID: NF:printoem.OEMSendPage
title: OEMSendPage function
author: windows-driver-content
description: The OEMSendPage function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.
old-location: print\oemsendpage.htm
old-project: print
ms.assetid: 9a3380d0-2d90-49ec-b97d-be55eb6eaaa5
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: OEMSendPage
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
req.alt-api: OEMSendPage
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
req.typenames: STDVARIABLEINDEX
req.product: Windows 10 or later.
---

# OEMSendPage function



## -description
The <code>OEMSendPage</code> function is called by GDI when it has finished drawing a physical page, so that the driver can send the page to the printer.



## -syntax

````
BOOL APIENTRY OEMSendPage(
   SURFOBJ *pso
);
````


## -parameters

### -param pso 


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