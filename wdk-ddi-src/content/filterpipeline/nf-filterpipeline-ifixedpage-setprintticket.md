---
UID: NF:filterpipeline.IFixedPage.SetPrintTicket
title: IFixedPage::SetPrintTicket method
author: windows-driver-content
description: The SetPrintTicket method associates a print ticket with the page.
old-location: print\ifixedpage_setprintticket.htm
old-project: print
ms.assetid: d899211a-e98d-45f6-9574-8b5f51658edf
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: filterpipeline_9cc3fcaf-d066-4468-b181-6d509fce403c.xml, print.ifixedpage_setprintticket, SetPrintTicket method [Print Devices], filterpipeline/IFixedPage::SetPrintTicket, SetPrintTicket, IFixedPage interface [Print Devices], SetPrintTicket method, IFixedPage::SetPrintTicket, SetPrintTicket method [Print Devices], IFixedPage interface, IFixedPage
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
req.lib: filterpipeline.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	filterpipeline.h
apiname:
-	IFixedPage.SetPrintTicket
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
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
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |
| **Library** | filterpipeline.h |