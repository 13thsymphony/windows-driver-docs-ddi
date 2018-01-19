---
UID : NF:filterpipeline.IFixedPage.SetPrintTicket
title : IFixedPage::SetPrintTicket method
author : windows-driver-content
description : The SetPrintTicket method associates a print ticket with the page.
old-location : print\ifixedpage_setprintticket.htm
old-project : print
ms.assetid : d899211a-e98d-45f6-9574-8b5f51658edf
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IFixedPage, IFixedPage::SetPrintTicket, SetPrintTicket
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : filterpipeline.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IFixedPage.SetPrintTicket
req.alt-loc : filterpipeline.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : Filterpipeline.idl
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : EXpsFontRestriction
---


# SetPrintTicket method
The <b>SetPrintTicket</b> method associates a print ticket with the page.

## Syntax

````
HRESULT SetPrintTicket(
  [in] IPartPrintTicket *pPrintTicket
);
````

## Parameters

`ppPrintTicket`




## Return Value

<b>SetPrintTicket</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | filterpipeline.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |