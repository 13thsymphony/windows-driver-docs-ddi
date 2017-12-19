---
UID: NF.prcomoem.IPrintCorePS2.DrvWriteSpoolBuf
title: IPrintCorePS2::DrvWriteSpoolBuf method
author: windows-driver-content
description: The IPrintCorePS2::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintcoreps2_drvwritespoolbuf.htm
old-project: print
ms.assetid: 25405dd8-730e-4de6-af44-9dd584ed3087
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPrintCorePS2, IPrintCorePS2::DrvWriteSpoolBuf, DrvWriteSpoolBuf
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
req.alt-api: IPrintCorePS2.DrvWriteSpoolBuf
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

# IPrintCorePS2::DrvWriteSpoolBuf method



## -description
The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.



## -syntax

````
HRESULT DrvWriteSpoolBuf(
  [in]  PDEVOBJ pdevobj ,
  [in]  PVOID   pBuffer ,
  [in]  DWORD   cbSize ,
  [out] DWORD   *pdwResult 
);
````


## -parameters

### -param pdevobj  [in]

Caller-supplied pointer to a <a href="print.devobj">DEVOBJ</a> structure.


### -param pBuffer  [in]

Caller-supplied pointer to a buffer containing data to be sent to the print spooler.


### -param cbSize  [in]

Caller-supplied value representing the size, in bytes, of the buffer pointed to by <i>pBuffer</i>. 


### -param pdwResult  [out]

Receives a method-supplied value representing the number of bytes sent to the spooler.


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
This method has the same behavior as <a href="print.iprintoemdriverps_drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>. This method is supported for any Pscript5 render plug-ins.


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

## -see-also
<dl>
<dt>
<a href="print.iprintoemdriverps_drvwritespoolbuf">IPrintOemDriverPS::DrvWriteSpoolBuf</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::DrvWriteSpoolBuf method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

