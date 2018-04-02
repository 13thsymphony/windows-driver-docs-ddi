---
UID: NF:filterpipeline.IFixedPage.SetPrintTicket
title: IFixedPage::SetPrintTicket method
author: windows-driver-content
description: The SetPrintTicket method associates a print ticket with the page.
old-location: print\ifixedpage_setprintticket.htm
old-project: print
ms.assetid: d899211a-e98d-45f6-9574-8b5f51658edf
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IFixedPage, IFixedPage interface [Print Devices], SetPrintTicket method, IFixedPage::SetPrintTicket, SetPrintTicket method [Print Devices], SetPrintTicket method [Print Devices], IFixedPage interface, SetPrintTicket,IFixedPage.SetPrintTicket, filterpipeline/IFixedPage::SetPrintTicket, filterpipeline_9cc3fcaf-d066-4468-b181-6d509fce403c.xml, print.ifixedpage_setprintticket
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
-	IFixedPage.SetPrintTicket
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---


# IFixedPage::SetPrintTicket method
The <b>SetPrintTicket</b> method associates a print ticket with the page.

## Syntax

```
HRESULT SetPrintTicket(
  IPartPrintTicket *ppPrintTicket
);
```

## Parameters

`ppPrintTicket`




## Return Value

<b>SetPrintTicket</b> returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | filterpipeline.h |