---
UID : NF:winppi.GdiGetDC
title : GdiGetDC function
author : windows-driver-content
description : The GdiGetDC function returns a handle to a printer's device context.
old-location : print\gdigetdc.htm
old-project : print
ms.assetid : f8aacb6d-4e8a-4fdb-902c-3d0efbc40f08
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : GdiGetDC
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
req.alt-api : GdiGetDC
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


# GdiGetDC function
The <b>GdiGetDC</b> function returns a handle to a printer's device context.

## Syntax

````
HDC GdiGetDC(
   HANDLE SpoolFileHandle
);
````

## Parameters

`SpoolFileHandle`

Caller-supplied spool file handle, obtained by a previous call to <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>.


## Return Value

If the operation succeeds, the function returns a device context handle. Otherwise the function returns <b>NULL</b>.

## Remarks

The <b>GdiGetDC</b> function is exported by gdi32.dll for use within a print processor's <a href="..\winsplp\nf-winsplp-printdocumentonprintprocessor.md">PrintDocumentOnPrintProcessor</a> function.

A print processor can call <b>GdiGetDC</b> to obtain a printer's device context handle anytime after calling <a href="..\winppi\nf-winppi-gdigetspoolfilehandle.md">GdiGetSpoolFileHandle</a>. The print processor can use the context handle to call Win32 device context functions, in order to perform such operations as applying transformations on the print image.

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