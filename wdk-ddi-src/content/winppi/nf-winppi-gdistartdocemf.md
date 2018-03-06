---
UID: NF:winppi.GdiStartDocEMF
title: GdiStartDocEMF function
author: windows-driver-content
description: The GdiStartDocEMF function performs initialization operations for an EMF-formatted print job.
old-location: print\gdistartdocemf.htm
old-project: print
ms.assetid: aca4534a-871e-4d86-b329-cb4f84611a29
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GdiStartDocEMF, GdiStartDocEMF function [Print Devices], gdifnc_11790088-e5fa-4817-a7d7-79c654814062.xml, print.gdistartdocemf, winppi/GdiStartDocEMF
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
-	GdiStartDocEMF
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---


# GdiStartDocEMF function
The <b>GdiStartDocEMF</b> function performs initialization operations for an EMF-formatted print job.

## Syntax

````
BOOL GdiStartDocEMF(
   HANDLE   SpoolFileHandle,
   DOCINFOW *pDocInfo
);
````

## Parameters

`SpoolFileHandle`

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.

`pDocInfo`

Caller-supplied pointer to a DOCINFOW structure (described in the Microsoft Window SDK documentation).


## Return Value

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise the function returns <b>FALSE</b>, and an error code can be obtained by calling <b>GetLastError</b>.

## Remarks

The <b>GdiStartDocEMF</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

The function performs initializations that must take place before a print job's EMF records can be played. The function calls the spooler's <b>StartDoc</b> function (described in the Window SDK documentation), which in turn calls the printer driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556296">DrvStartDoc</a> function.

The print processor must set the <b>lpszOutput</b> member of the DOCINFOW structure to the output file name contained in the <a href="..\winsplp\ns-winsplp-_printprocessoropendata.md">PRINTPROCESSOROPENDATA</a> structure, previously received by the <a href="..\winsplp\nf-winsplp-openprintprocessor.md">OpenPrintProcessor</a> function.

The print processor must set the <b>lpszDocName</b> member of the DOCINFOW structure to the document name pointer, previously received by the <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | winppi.h (include Winppi.h) |
| **Library** | Gdi32.Lib |
| **DLL** | Gdi32.dll |

## See Also

<a href="..\winppi\nf-winppi-gdienddocemf.md">GdiEndDocEMF</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20GdiStartDocEMF function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>