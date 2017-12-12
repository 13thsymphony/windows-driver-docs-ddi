---
UID: NF.winppi.GdiGetSpoolFileHandle
title: GdiGetSpoolFileHandle function
author: windows-driver-content
description: The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file.
old-location: print\gdigetspoolfilehandle.htm
old-project: print
ms.assetid: c820ee94-29c2-4478-884c-49dd68cd713a
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: GdiGetSpoolFileHandle
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winppi.h
req.include-header: Winppi.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GdiGetSpoolFileHandle
req.alt-loc: Gdi32.dll,Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll,GDI32Full.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Gdi32.Lib
req.dll: Gdi32.dll
req.irql: 
req.product: Windows 10 or later.
---

# GdiGetSpoolFileHandle function



## -description
The <b>GdiGetSpoolFileHandle</b> function returns a handle to a print job's EMF file.



## -syntax

````
HANDLE GdiGetSpoolFileHandle(
   LPWSTR     pwszPrinterName,
   LPDEVMODEW pDevmode,
   LPWSTR     pwszDocName
);
````


## -parameters

### -param pwszPrinterName 

Caller-supplied pointer to a string representing the name of the target printer. See the following Remarks section.


### -param pDevmode 

Caller-supplied pointer to a <a href="display.devmodew">DEVMODEW</a> structure. See the following Remarks section.


### -param pwszDocName 

Caller-supplied pointer to the print job's document name. See the following Remarks section.


## -returns
If the operation succeeds, the function returns a spool file handle. Otherwise the function returns <b>NULL</b>.


## -remarks
The <b>GdiGetSpoolFileHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="print.printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

When a print processor calls <b>GdiGetSpoolFileHandle</b>, it should supply arguments as illustrated in the following table.

<i>pwszPrinterName</i>

Pointer to the printer name received by the print processor's <a href="print.openprintprocessor">OpenPrintProcessor</a> function.

<i>pDevmode</i>

Pointer to the <a href="display.devmodew">DEVMODEW</a> structure contained in the <a href="print.printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure, received by the print processor's <a href="print.openprintprocessor">OpenPrintProcessor</a> function.

<i>pwszDocName</i>

Document name pointer received by the print processor's <a href="print.printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function.

A print processor must call the <b>GdiGetSpoolFileHandle</b> function before calling any other GDI printing functions, because the returned handle must be passed to the other functions. The function calls OpenPrinter to open a connection to the printer, and CreateDC to create a device context for drawing. The print processor can obtain the device context's handle by calling <a href="print.gdigetdc">GdiGetDC</a>.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Winppi.h (include Winppi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Gdi32.Lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Gdi32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.gdideletespoolfilehandle">GdiDeleteSpoolFileHandle</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GdiGetSpoolFileHandle function%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

