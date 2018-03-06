---
UID: NF:winspool.GetJobNamedPropertyValue
title: GetJobNamedPropertyValue function
author: windows-driver-content
description: Retrieves the value of the named property for the specified print job on the specified printer.
old-location: print\getjobnamedpropertyvalue.htm
old-project: print
ms.assetid: A9256A7B-B851-498C-94C3-95268D079828
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: GetJobNamedPropertyValue, GetJobNamedPropertyValue function [Print Devices], print.getjobnamedpropertyvalue, winspool/GetJobNamedPropertyValue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winspool.h
req.include-header: Winspool.h
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
req.lib: WinSpool.lib
req.dll: Spoolss.dll; WinSpool.drv
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	spoolss.dll
-	WinSpool.drv
api_name:
-	GetJobNamedPropertyValue
product: Windows
targetos: Windows
req.typenames: BIDI_TYPE
req.product: Windows 10 or later.
---


# GetJobNamedPropertyValue function
Retrieves the value of the named property for the specified print job on the specified printer.

## Syntax

````
DWORD WINAPI GetJobNamedPropertyValue(
  _In_  HANDLE             hPrinter,
  _In_  DWORD              JobId,
  _In_  PCWSTR             pszName,
  _Out_ PrintPropertyValue *pValue
);
````

## Parameters

`hPrinter`

A handle to the printer object of interest. Use the <a href="https://msdn.microsoft.com/8bbb46a8-2bba-4d15-a2e2-4770b52d2505">OpenPrinter</a>, <a href="https://msdn.microsoft.com/e2370ae4-4475-4ccc-a6f9-3d33d1370054">OpenPrinter2</a>, or the <a href="https://msdn.microsoft.com/ffc4fee8-46c6-47ad-803d-623bf8efdefd">AddPrinter</a> function to retrieve a printer handle.

`JobId`

Identifier that specifies the print job. You obtain a print job identifier by calling the <a href="https://msdn.microsoft.com/cfafa874-6022-4bf4-bf3d-096213eb0c98">AddJob</a> function or the <a href="..\printoem\nf-printoem-oemstartdoc.md">StartDoc</a> function.

`pszName`

Name of the property whose value will be retrieved.

`pValue`

Value of the named property. The caller needs to free this using the <a href="..\winspool\nf-winspool-freeprintpropertyvalue.md">FreePrintPropertyValue</a> function.


## Return Value

If the operation succeeds, the function returns <b>ERROR_SUCCESS</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | winspool.h (include Winspool.h) |
| **Library** | WinSpool.lib |
| **DLL** | Spoolss.dll; WinSpool.drv |