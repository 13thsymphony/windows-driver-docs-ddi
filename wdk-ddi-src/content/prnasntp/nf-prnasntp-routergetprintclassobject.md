---
UID: NF.prnasntp.RouterGetPrintClassObject
title: RouterGetPrintClassObject function
author: windows-driver-content
description: The RouterGetPrintClassObject function enumerates the list of print providers, searching for the print provider with the specified name and interface ID.
old-location: print\routergetprintclassobject.htm
old-project: print
ms.assetid: e2df591d-59bd-4aae-ac1b-8fdf01da3ea7
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: RouterGetPrintClassObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prnasntp.h
req.include-header: Prnasntp.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RouterGetPrintClassObject
req.alt-loc: Spoolss.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
req.product: Windows 10 or later.
---

# RouterGetPrintClassObject function



## -description
The <code>RouterGetPrintClassObject</code> function enumerates the list of print providers, searching for the print provider with the specified name and interface ID. 


## -syntax

````
HRESULT RouterGetPrintClassObject(
  _In_  PCWSTR pPrinter,
  _In_  REFIID riid,
  _Out_ VOID   **ppv
);
````


## -parameters

### -param pPrinter [in]

A pointer to a null-terminated string that contains the name of the printer or print server.

### -param riid [in]

The identifier of the requested COM interface.

### -param ppv [out]

A pointer to a variable that supplies the address of the COM interface requested in the <i>iid</i> parameter.

## -returns
This function returns S_OK on success, and a standard COM error code otherwise.

## -remarks


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
<dt>Prnasntp.h (include Prnasntp.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Spoolss.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>Spoolss.dll</dt>
</dl>
</td>
</tr>
</table>