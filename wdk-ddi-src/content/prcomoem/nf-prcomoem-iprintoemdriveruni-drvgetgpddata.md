---
UID: NF:prcomoem.IPrintOemDriverUni.DrvGetGPDData
title: IPrintOemDriverUni::DrvGetGPDData method
author: windows-driver-content
description: The IPrintOemDriverUni::DrvGetGPDData method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's GPD file.
old-location: print\iprintoemdriveruni_drvgetgpddata.htm
old-project: print
ms.assetid: cebe8972-4e5a-4382-ac1b-4c326dea46b1
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintOemDriverUni, IPrintOemDriverUni::DrvGetGPDData, DrvGetGPDData
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
req.alt-api: IPrintOemDriverUni.DrvGetGPDData
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
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---

# IPrintOemDriverUni::DrvGetGPDData method



## -description
The <code>IPrintOemDriverUni::DrvGetGPDData</code> method is provided by the Unidrv driver so that rendering plug-ins can obtain data defined in a printer's <a href="wdkgloss.g#wdkgloss.generic_printer_description__gpd_#wdkgloss.generic_printer_description__gpd_"><i>GPD</i></a> file.



## -syntax

````
HRESULT DrvGetGPDData(
   PDEVOBJ pdevobj,
   DWORD   dwType,
   PVOID   pInputData,
   PVOID   pBuffer,
   DWORD   cbSize,
   PDWORD  pcbNeeded
);
````


## -parameters

### -param pdevobj 

Caller-supplied pointer to a <a href="..\printoem\ns-printoem-_devobj.md">DEVOBJ</a> structure.


### -param dwType 

Caller-supplied flag indicating the type of GPD data being requested. Currently, the following flag is the only one defined:

<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
GPD_OEMCUSTOMDATA

</td>
<td>
The method returns the string associated with a GPD file's *<b>OEMCustomData</b> entry.

</td>
</tr>
</table>
 


### -param pInputData 

Reserved. Must be zero.


### -param pBuffer 

Caller-supplied pointer to a buffer to receive the requested information.


### -param cbSize 

Caller-supplied size, in bytes, of the buffer pointed to by <i>pBuffer</i>.


### -param pcbNeeded 

Receives the driver-supplied minimum buffer size, in bytes, required to contain the requested information.


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
If the buffer specified by <i>pBuffer</i> and <i>cbSize</i> is too small to receive the requested information, Unidrv supplies the required buffer size in the location pointed to by <i>pcbNeeded</i>, returns E_FAIL, and sets the error code to ERROR_INSUFFICIENT_BUFFER.


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