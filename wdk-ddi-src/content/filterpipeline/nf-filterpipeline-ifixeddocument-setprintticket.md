---
UID: NF:filterpipeline.IFixedDocument.SetPrintTicket
title: IFixedDocument::SetPrintTicket method
author: windows-driver-content
description: The SetPrintTicket method inserts a print ticket into the fixed document.
old-location: print\ifixeddocument_setprintticket.htm
old-project: print
ms.assetid: 701c53d5-bb1e-4003-9505-19b9c46689c6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IFixedDocument, IFixedDocument interface [Print Devices], SetPrintTicket method, IFixedDocument::SetPrintTicket, SetPrintTicket method [Print Devices], SetPrintTicket method [Print Devices], IFixedDocument interface, SetPrintTicket,IFixedDocument.SetPrintTicket, filterpipeline/IFixedDocument::SetPrintTicket, filterpipeline_96d89fc9-899f-4ede-8da5-898471f6b769.xml, print.ifixeddocument_setprintticket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: filterpipeline.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: Filterpipeline.idl
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	filterpipeline.h
api_name:
-	IFixedDocument.SetPrintTicket
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# SetPrintTicket method
The <b>SetPrintTicket</b> method inserts a print ticket into the fixed document.

## Syntax

````
HRESULT SetPrintTicket(
  [in] IPartPrintTicket *pPrintTicket
);
````

## Parameters

`pPrintTicket`

A pointer to the print ticket to be inserted.


## Return Value

<b>SetPrintTicket</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |