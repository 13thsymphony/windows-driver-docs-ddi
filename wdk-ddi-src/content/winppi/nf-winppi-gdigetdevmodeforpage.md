---
UID : NF:winppi.GdiGetDevmodeForPage
title : GdiGetDevmodeForPage function
author : windows-driver-content
description : The GdiGetDevmodeForPage function returns DEVMODEW structures for the specified and previous pages of a print job.
old-location : print\gdigetdevmodeforpage.htm
old-project : print
ms.assetid : 3410e8b1-820f-4892-8d26-d803e3f943da
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : GdiGetDevmodeForPage
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : winppi.h
req.include-header : Winppi.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : GdiGetDevmodeForPage
req.alt-loc : Gdi32.dll,Ext-MS-Win-GDI-Internal-Desktop-L1-1-0.dll,GDI32Full.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Gdi32.Lib
req.dll : Gdi32.dll
req.irql : 
req.typenames : DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product : Windows 10 or later.
---


# GdiGetDevmodeForPage function
The <b>GdiGetDevmodeForPage</b> function returns <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structures for the specified and previous pages of a print job.

## Syntax

````
BOOL GdiGetDevmodeForPage(
   HANDLE    SpoolFileHandle,
   DWORD     dwPageNumber,
   PDEVMODEW *pCurrDM,
   PDEVMODEW *pLastDM
);
````

## Parameters

`SpoolFileHandle`

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.

`dwPageNumber`

Caller-supplied number of the page for which <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> contents are to be returned.

`pCurrDM`

Caller-supplied location to receive a pointer to a DEVMODE structure for the page specified by <i>dwPageNumber</i>.

`pLastDM`

Caller-supplied location to receive a pointer to a DEVMODE structure for the page previous to the one specified by <i>dwPageNumber</i>.


## Return Value

If the operation succeeds, the function returns <b>TRUE</b>. Otherwise it returns <b>FALSE</b>.

## Remarks

The <b>GdiGetDevmodeForPage</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

Before calling <a href="..\winppi\nf-winppi-gdiplaypageemf.md">GdiPlayPageEMF</a> to execute a page's EMF instructions, a print processor must call <b>GdiGetDevmodeForPage</b> to determine if the DEVMODE structure associated with the page to be printed is the same as that of the last page printed. If the two returned DEVMODE structures are not identical, the print processor must perform the following steps, in order, before calling <b>GdiPlayPageEMF</b> for the page:

Call <a href="..\winppi\nf-winppi-gdiendpageemf.md">GdiEndPageEMF</a>.

Call <a href="..\winppi\nf-winppi-gdiresetdcemf.md">GdiResetDCEMF</a>, specifying the DEVMODE pointed to by <i>pCurrDM</i>.

Call <a href="..\winppi\nf-winppi-gdistartpageemf.md">GdiStartPageEMF</a>.

For additional information, see <a href="https://msdn.microsoft.com/2ad62308-ab42-4475-ac42-f753d5091251">Using GDI Functions in Print Processors</a>.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | winppi.h (include Winppi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |