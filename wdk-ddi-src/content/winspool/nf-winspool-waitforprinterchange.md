---
UID: NF.winspool.WaitForPrinterChange
title: WaitForPrinterChange
author: windows-driver-content
description: .
old-location: print\waitforprinterchange.htm
old-project: print
ms.assetid: BD9DD9C4-D736-42DC-A55F-7F299351FA65
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: WaitForPrinterChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WaitForPrinterChange
req.alt-loc: Winspool.h
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
req.iface: 
req.product: Windows 10 or later.
---

# WaitForPrinterChange function



## -description
<p></p>


## -syntax

````
DWORD WINAPI WaitForPrinterChange(
   HANDLE hPrinter,
   DWORD  Flags
);
````


## -parameters
<dl>

### -param <i>hPrinter</i> 

<dd></dd>

### -param <i>Flags</i> 

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Winspool.h</dt>
</dl>
</td>
</tr>
</table>