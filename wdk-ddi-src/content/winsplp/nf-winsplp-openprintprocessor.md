---
UID: NF.winsplp.OpenPrintProcessor
title: OpenPrintProcessor function
author: windows-driver-content
description: A print processor's OpenPrintProcessor function prepares the print processor for printing a job and returns a handle.
old-location: print\openprintprocessor.htm
old-project: print
ms.assetid: bab79fb6-1bb0-48ec-9d60-fcb6e679b758
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: OpenPrintProcessor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: OpenPrintProcessor
req.alt-loc: Nwprint.lib,Nwprint.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Nwprint.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# OpenPrintProcessor function



## -description
A print processor's <code>OpenPrintProcessor</code> function prepares the print processor for printing a job and returns a handle.


## -syntax

````
HANDLE OpenPrintProcessor(
  _In_ LPWSTR                  pPrinterName,
  _In_ PPRINTPROCESSOROPENDATA pPrintProcessorOpenData
);
````


## -parameters

### -param pPrinterName [in]

Caller-supplied pointer to the name of the printer for which the print processor is being opened.

### -param pPrintProcessorOpenData [in]

Caller-supplied pointer to a <a href="print.printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure.

## -returns
If the operation succeeds, the function should return a handle that can be used as an input argument for subsequent calls to <a href="print.printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>, <a href="print.controlprintprocessor">ControlPrintProcessor</a>, and <a href="print.closeprintprocessor">ClosePrintProcessor</a>. If the operation fails, the function should call <b>SetLastError</b> to set an error code, and then return <b>NULL</b>.

## -remarks
Print processors are required to export an <code>OpenPrintProcessor</code> function. The spooler calls the function when a print job is available. The function should perform initialization operations that are required before a job can be processed, based on the job's data type.

The function must return a handle. Typically, the handle is a pointer to an internal structure. The structure must contain a pointer to the printer's name and a pointer to the printer's <a href="display.devmodew">DEVMODEW</a> structure, both of which are received in the <a href="print.printprocessoropendata">PRINTPROCESSOROPENDATA</a> structure. These two pointers are required by the print processor's <a href="print.printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a> function, and this latter function receives the handle as input when the spooler calls it.

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
<dt>Winsplp.h (include Winsplp.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Nwprint.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="print.printprocessoropendata">PRINTPROCESSOROPENDATA</a>
</dt>
<dt>
<a href="print.printdocumentonprintprocessor">PrintDocumentOnPrintProcessor</a>
</dt>
<dt>
<a href="print.controlprintprocessor">ControlPrintProcessor</a>
</dt>
<dt>
<a href="print.closeprintprocessor">ClosePrintProcessor</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20OpenPrintProcessor function%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
