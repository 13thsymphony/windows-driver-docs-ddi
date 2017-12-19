---
UID: NF.prcomoem.IPrintOemDriverPS.DrvWriteSpoolBuf
title: IPrintOemDriverPS::DrvWriteSpoolBuf method
author: windows-driver-content
description: The IPrintOemDriverPS::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that rendering plug-ins can send printer data to the spooler.
old-location: print\iprintoemdriverps_drvwritespoolbuf.htm
old-project: print
ms.assetid: 91eb36b3-ea05-4a5e-8bba-47c262a4fa4a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemDriverPS, IPrintOemDriverPS::DrvWriteSpoolBuf, DrvWriteSpoolBuf
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemDriverPS.DrvWriteSpoolBuf
req.alt-loc: prcomoem.h
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

# IPrintOemDriverPS::DrvWriteSpoolBuf method



## -description
The <code>IPrintOemDriverPS::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-ins</a> can send printer data to the spooler.



## -syntax

````
HRESULT DrvWriteSpoolBuf(
        PDEVOBJ pdevobj,
        PVOID   pBuffer,
        DWORD   cbSize,
  [out] DWORD   *pdwResult
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param pBuffer 

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.


### -param cbSize 

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>.


### -param pdwResult [out]

Receives a method-supplied value representing the number of bytes sent to the spooler.


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
Rendering plug-ins are described in <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>