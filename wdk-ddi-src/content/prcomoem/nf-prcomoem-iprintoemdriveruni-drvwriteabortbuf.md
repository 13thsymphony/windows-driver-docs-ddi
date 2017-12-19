---
UID: NF.prcomoem.IPrintOemDriverUni.DrvWriteAbortBuf
title: IPrintOemDriverUni::DrvWriteAbortBuf method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvWriteAbortBuf method is provided by the Unidrv driver to allow an OEM rendering plug-in to send printer clean-up code after a user terminates a print job.
old-location: print\iprintoemdriveruni_drvwriteabortbuf.htm
old-project: print
ms.assetid: 4f7aff9b-32cf-42a0-ba3b-ddc87ecdb8c3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni::DrvWriteAbortBuf, DrvWriteAbortBuf
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
req.alt-api: IPrintOemDriverUni.DrvWriteAbortBuf
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

# IPrintOemDriverUni::DrvWriteAbortBuf method



## -description
The <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> method is provided by the Unidrv driver to allow an OEM <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> to send printer clean-up code after a user terminates a print job.



## -syntax

````
HRESULT DrvWriteAbortBuf(
   PDEVOBJ pdevobj,
   PVOID   pBuffer,
   DWORD   cbSize,
   DWORD   dwWait
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param pBuffer 

Caller-supplied pointer to a buffer containing a code fragment to be sent to the printer.


### -param cbSize 

Caller-supplied number of bytes in the buffer pointed to by <i>pBuffer</i>.


### -param dwWait 

Caller-supplied length of time the printer must wait, in milliseconds, before it can start a new print job after the current job is aborted. 


## -returns
The method must return one of the following values.
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation succeeded.
<dl>
<dt><b>E_FAIL</b></dt>
</dl>The operation failed.
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>The method is not implemented.

 


## -remarks
OEMs use <a href="print.iprintoemdriveruni_drvwritespoolbuf">IPrintOemDriverUni::DrvWriteSpoolBuf</a> to send output to the printer. If a print job is terminated by the user, <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> returns E_FAIL and can no longer be used to send any data to the printer. When this occurs, certain printers must have a clean-up code fragment sent to them, resetting their states before they can start new print jobs. For these printers, <code>IPrintOemDriverUni::DrvWritetAbortBuf</code> is used to send this code fragment to the printer.

<code>IPrintOemDriverUni::DrvWriteAbortBuf</code> can only be called after <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> has returned E_FAIL. <code>IPrintOemDriverUni::DrvWriteAbortBuf</code> should not be called more than once per job. 

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