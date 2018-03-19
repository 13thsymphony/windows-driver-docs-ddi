---
UID: NF:winppi.GdiGetSpoolFileHandle
title: GdiGetSpoolFileHandle function
author: windows-driver-content
description: The GdiGetSpoolFileHandle function returns a handle to a print job's EMF file.
old-location: print\gdigetspoolfilehandle.htm
old-project: print
ms.assetid: c820ee94-29c2-4478-884c-49dd68cd713a
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GdiGetSpoolFileHandle, GdiGetSpoolFileHandle function [Print Devices], gdifnc_f7231fd8-33b0-4047-90ba-e5e2c9c37814.xml, print.gdigetspoolfilehandle, winppi/GdiGetSpoolFileHandle
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Gdi32.dll
-	Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll
-	GDI32Full.dll
api_name:
-	GdiGetSpoolFileHandle
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---


# GdiGetSpoolFileHandle function
The <b>GdiGetSpoolFileHandle</b> function returns a handle to a print job's EMF file.

## Syntax

````
HANDLE GdiGetSpoolFileHandle(
   LPWSTR     pwszPrinterName,
   LPDEVMODEW pDevmode,
   LPWSTR     pwszDocName
);
````

## Parameters

`pwszPrinterName`

Caller-supplied pointer to a string representing the name of the target printer. See the following Remarks section.

`pDevmode`

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. See the following Remarks section.

`pwszDocName`

Caller-supplied pointer to the print job's document name. See the following Remarks section.


## Return Value

If the operation succeeds, the function returns a spool file handle. Otherwise the function returns <b>NULL</b>.

## Remarks

The <b>GdiGetSpoolFileHandle</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

When a print processor calls <b>GdiGetSpoolFileHandle</b>, it should supply arguments as illustrated in the following table.

<table>
<tr>
<th>Parameter</th>
<th>Argument</th>
</tr>
<tr>
<td>
<i>pwszPrinterName</i>

</td>
<td>
Pointer to the printer name received by the print processor's <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a> function.

</td>
</tr>
<tr>
<td>
<i>pDevmode</i>

</td>
<td>
Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure contained in the <a href="..\winsplp\ns-winsplp-_printprocessoropendata.md">PRINTPROCESSOROPENDATA</a> structure, received by the print processor's <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a> function.

</td>
</tr>
<tr>
<td>
<i>pwszDocName</i>

</td>
<td>
Document name pointer received by the print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

</td>
</tr>
</table>
 

A print processor must call the <b>GdiGetSpoolFileHandle</b> function before calling any other GDI printing functions, because the returned handle must be passed to the other functions. The function calls OpenPrinter to open a connection to the printer, and CreateDC to create a device context for drawing. The print processor can obtain the device context's handle by calling <a href="..\winppi\nf-winppi-gdigetdc.md">GdiGetDC</a>.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | winppi.h (include Winppi.h) |
| **Library** | Gdi32.Lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\winppi\nf-winppi-gdideletespoolfilehandle.md">GdiDeleteSpoolFileHandle</a>