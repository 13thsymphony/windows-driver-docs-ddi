---
UID: NF:winddiui.DrvSplEndDoc
title: DrvSplEndDoc function
author: windows-driver-content
description: .
old-location: print\drvsplenddoc.htm
old-project: print
ms.assetid: 7972fd88-ca99-4a42-8476-754b26eb118c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: DrvSplEndDoc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winddiui.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DrvSplEndDoc
req.alt-loc: winddiui.h
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
req.typenames: WINBIO_VERSION, *PWINBIO_VERSION
req.product: Windows 10 or later.
---

# DrvSplEndDoc function



## -description




## -syntax

````
VOID WINAPI DrvSplEndDoc(
   HANDLE hDriver
);
````


## -parameters

### -param hDriver 


## -returns
This function does not return a value.

The <b>DrvSplEndDoc</b> function is obsolete, and is supported only so that user-mode rendering DLLs, optionally supplied with Windows NT 4.0 drivers, will execute under Windows 2000 and later. Use <a href="..\winddiui\nf-winddiui-drvdocumentevent.md">DrvDocumentEvent</a> instead of this function.

The <b>DrvSplEndDoc</b> function enables a user-mode rendering DLL to perform operations associated with the end of a print job.

To supply user-mode image-rendering code for printers, see <a href="https://msdn.microsoft.com/1e63d01e-8cf2-488a-89e8-d4a3ff5cfe19">Choosing User Mode or Kernel Mode</a>.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winddiui.h</dt>
</dl>
</td>
</tr>
</table>