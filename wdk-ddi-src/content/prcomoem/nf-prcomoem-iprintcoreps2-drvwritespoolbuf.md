---
UID: NF:prcomoem.IPrintCorePS2.DrvWriteSpoolBuf
title: IPrintCorePS2::DrvWriteSpoolBuf method
author: windows-driver-content
description: The IPrintCorePS2::DrvWriteSpoolBuf method is provided by the Pscript5 driver so that a rendering plug-in can send printer data to the spooler.
old-location: print\iprintcoreps2_drvwritespoolbuf.htm
old-project: print
ms.assetid: 25405dd8-730e-4de6-af44-9dd584ed3087
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DrvWriteSpoolBuf method [Print Devices], DrvWriteSpoolBuf method [Print Devices], IPrintCorePS2 interface, DrvWriteSpoolBuf,IPrintCorePS2.DrvWriteSpoolBuf, IPrintCorePS2, IPrintCorePS2 interface [Print Devices], DrvWriteSpoolBuf method, IPrintCorePS2::DrvWriteSpoolBuf, prcomoem/IPrintCorePS2::DrvWriteSpoolBuf, print.iprintcoreps2_drvwritespoolbuf, print_unidrv-pscript_rendering_56d81faa-5b82-4d07-beb1-9a8a82fc7409.xml
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
req.lib: 
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
-	IPrintCorePS2.DrvWriteSpoolBuf
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# DrvWriteSpoolBuf method
The <code>IPrintCorePS2::DrvWriteSpoolBuf</code> method is provided by the Pscript5 driver so that a <a href="https://msdn.microsoft.com/e55ca083-2790-4929-9e5b-6fce49eb0404">rendering plug-in</a> can send printer data to the spooler.

## Syntax

````
HRESULT DrvWriteSpoolBuf(
  [in]  PDEVOBJ pdevobj ,
  [in]  PVOID   pBuffer ,
  [in]  DWORD   cbSize ,
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

This method has the same behavior as <a href="https://msdn.microsoft.com/library/windows/hardware/ff553103">IPrintOemDriverPS::DrvWriteSpoolBuf</a>. This method is supported for any Pscript5 render plug-ins.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553103">IPrintOemDriverPS::DrvWriteSpoolBuf</a>



<a href="..\prcomoem\nn-prcomoem-iprintcoreps2.md">IPrintCorePS2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintCorePS2::DrvWriteSpoolBuf method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>