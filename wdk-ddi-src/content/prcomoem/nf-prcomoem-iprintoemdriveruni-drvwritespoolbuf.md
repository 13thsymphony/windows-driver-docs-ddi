---
UID: NF:prcomoem.IPrintOemDriverUni.DrvWriteSpoolBuf
title: IPrintOemDriverUni::DrvWriteSpoolBuf method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvWriteSpoolBuf method is provided by the Unidrv driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintoemdriveruni_drvwritespoolbuf.htm
old-project: print
ms.assetid: e019b88a-bffe-44d2-8031-de37b6a1cf1c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvWriteSpoolBuf method [Print Devices], DrvWriteSpoolBuf method [Print Devices], IPrintOemDriverUni interface, DrvWriteSpoolBuf,IPrintOemDriverUni.DrvWriteSpoolBuf, IPrintOemDriverUni, IPrintOemDriverUni interface [Print Devices], DrvWriteSpoolBuf method, IPrintOemDriverUni::DrvWriteSpoolBuf, prcomoem/IPrintOemDriverUni::DrvWriteSpoolBuf, print.iprintoemdriveruni_drvwritespoolbuf, print_unidrv-pscript_rendering_ba569121-3277-447a-a53b-3de6e06fd182.xml
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: prcomoem.h
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prcomoem.h
api_name:
-	IPrintOemDriverUni.DrvWriteSpoolBuf
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# DrvWriteSpoolBuf method
The <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> method is provided by the Unidrv driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.

## Syntax

````
HRESULT DrvWriteSpoolBuf(
        PDEVOBJ pdevobj,
        PVOID   pBuffer,
        DWORD   cbSize,
  [out] DWORD   *pdwResult
);
````

## Parameters

`pdevobj`

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.

`pBuffer`

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.

`cbSize`

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>.

`pdwResult`

Receives a method-supplied value representing the number of bytes sent to the spooler.


## Return Value

The method must return one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_FAIL</b></dt>
</dl>
</td>
<td width="60%">
The operation failed.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_NOTIMPL</b></dt>
</dl>
</td>
<td width="60%">
The method is not implemented.

</td>
</tr>
</table>

## Remarks

OEMs use the Unidrv helper function <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> to send output to the printer. If a print job is terminated by the user, <code>IPrintOemDriverUni::DrvWriteSpoolBuf</code> returns E_FAIL and can no longer be used to send any data to the printer. When this occurs, certain printers must have a clean-up code fragment sent to them, resetting their states before they can start new print jobs. For these printers, <a href="https://msdn.microsoft.com/library/windows/hardware/ff553135">IPrintOemDriverUni::DrvWriteAbortBuf</a> can be used to send this code fragment to the printer. 

Rendering plug-ins are described in <a href="https://msdn.microsoft.com/b7761209-1f6f-4288-af47-4ed855c2e629">Customizing Microsoft's Printer Drivers</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |