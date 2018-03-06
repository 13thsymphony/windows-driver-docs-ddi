---
UID: NF:winppi.GdiGetPageCount
title: GdiGetPageCount function
author: windows-driver-content
description: The GdiGetPageCount function returns the number of pages in a print job.
old-location: print\gdigetpagecount.htm
old-project: print
ms.assetid: 0a101b59-c610-4158-97a8-002222a94309
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GdiGetPageCount, GdiGetPageCount function [Print Devices], gdifnc_f34bbc65-29f2-47b1-aec3-523af01a804c.xml, print.gdigetpagecount, winppi/GdiGetPageCount
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
-	GdiGetPageCount
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---


# GdiGetPageCount function
The <b>GdiGetPageCount</b> function returns the number of pages in a print job.

## Syntax

````
DWORD GdiGetPageCount(
   HANDLE SpoolFileHandle
);
````

## Parameters

`SpoolFileHandle`

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## Return Value

If the operation succeeds, the function returns the number of pages in the current print job. Otherwise the function returns zero.

## Remarks

The <b>GdiGetPageCount</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

<div class="alert"><b>Note</b>  The <b>GdiGetPageCount</b> function does not return until all pages have been spooled, even if the print server administrator has specified that print jobs should be printed during spooling. Therefore, this function should not be used unless it is necessary to obtain the total page count before document processing can begin, such as for printing pages in reverse order.<p class="note">Usually, a better method for determining the page count is to count the number of calls made to <a href="..\winppi\nf-winppi-gdigetpagehandle.md">GdiGetPageHandle</a>.

</div>
<div> </div>
For additional information about this set of functions, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | winppi.h (include Winppi.h) |
| **Library** | Gdi32.Lib |
| **DLL** | Gdi32.dll |